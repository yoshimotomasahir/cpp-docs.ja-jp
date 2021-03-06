---
title: /Zc:inline (参照されない COMDAT の除去) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/01/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 067ba5dad4e0751a86835ea56c536a5b7250485d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379589"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (参照されない COMDAT の除去)

COMDAT であるか内部リンケージのみを持つ、参照されていない関数またはデータを削除します。 ときに **/Zc:inline**を指定すると、コンパイラは、インライン データまたはインライン関数を使用する翻訳単位でのデータまたは関数の定義する必要がありますも含まれることが必要です。

## <a name="syntax"></a>構文

> **/Zc:inline**[**-**]

## <a name="remarks"></a>コメント

ときに **/Zc:inline**を指定すると、コンパイラが参照されていない COMDAT 関数またはデータ、または関数または内部リンケージのみを持つデータのシンボル情報を生成しません。 この最適化はリリース ビルドでは、リンカーによって実行される作業の一部を簡略化またはリンカー オプション[/opt:ref による](../../build/reference/opt-optimizations.md)を指定します。 コンパイラによってこの最適化が実行されると、.obj ファイルのサイズを大幅に縮小し、リンカーの速度を向上させることができます。 このコンパイラ オプションが有効になっていません最適化が無効にした場合 ([/Od](../../build/reference/od-disable-debug.md)) 場合や[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)が指定されています。

既定では、このオプションはオフ (**/Zc:inline-**)。 [寛容/-](permissive-standards-conformance.md)オプションが有効にしません **/Zc:inline**です。

場合 **/Zc:inline**が指定されている、コンパイラは、c++ 11 の要件のすべての関数が宣言されている`inline`使用される場合、同じ翻訳単位で使用可能な定義を持つ必要があります。 オプションが指定されていない場合、Microsoft コンパイラにより、宣言された関数を呼び出す非準拠コード`inline`定義が表示されていない場合でもです。 詳細については、C++11 標準のセクション 3.2 およびセクション 7.1.2 を参照してください。 このコンパイラ オプションは、Visual Studio 2013 更新プログラム 2 で導入されました。

使用する、 **/Zc:inline**オプション、非対応のコードを更新します。

この例は、どのように定義のないインライン関数宣言の非準拠の使用でもコンパイルおよびリンク時に示しています。 既定値 **/Zc:inline-** オプションを使用します。

```cpp
// example.h
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#pragma once

class Example {
public:
   inline void inline_call(); // declared but not defined inline
   void normal_call();
   Example() {};
};
```

```cpp
// example.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include <stdio.h>
#include "example.h"

void Example::inline_call() {
   printf("inline_call was called.\n"); 
}

void Example::normal_call() {
   printf("normal_call was called.\n"); 
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file
}
```

```cpp
// zcinline.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include "example.h"

void main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

ときに **/Zc:inline**が有効になって、同じコード、 [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)エラー、コンパイラが、非インライン コードの本体を生成しませんので`Example::inline_call`example.obj 内です。これにより、`main` 内のインライン展開されていない呼び出しは、定義されていない外部シンボルを参照します。

このエラーを解決するには、`inline` キーワードを `Example::inline_call` の宣言から削除するか、`Example::inline_call` の定義をヘッダー ファイルに移動するか、`Example` の実装を main.cpp に移動します。 次の例では、定義をヘッダー ファイルに移動します。そこでは、ヘッダーを含む任意の呼び出し元から定義を参照できます。

```cpp
// example2.h
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#pragma once
#include <stdio.h>

class Example2 {
public:
   inline void inline_call() {
      printf("inline_call was called.\n"); 
   }
   void normal_call();
   Example2() {};
};
```

```cpp
// example2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void Example2::normal_call() {
   printf("normal_call was called.\n"); 
   inline_call(); 
}
```

```cpp
// zcinline2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **言語**プロパティ ページ。

1. 変更、**参照されていないコードとデータを削除**プロパティを選択し**OK**です。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
