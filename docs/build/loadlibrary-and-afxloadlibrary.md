---
title: LoadLibrary と AfxLoadLibrary |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/24/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- LoadLibrary
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc3be5d374995c657021952184794f146c37f4dc
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753589"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary と AfxLoadLibrary

呼び出しを処理[LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) (または[AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) に DLL に明示的にリンクします。 この関数が正常終了した場合、呼び出し元プロセスのアドレス空間に指定された DLL が割り当てられ、DLL へのハンドルが返されます。このハンドルは、`GetProcAddress` や `FreeLibrary` など、明示的リンクに必要な他の関数で使用できます。

`LoadLibrary` は、暗黙リンクと同じ検索シーケンスで DLL を探します。 システムが DLL を見つけられない場合、またはエントリ ポイント関数が FALSE を返した場合、`LoadLibrary` は NULL を返します。 `LoadLibrary` への呼び出しで指定される DLL モジュールが呼び出し元プロセスのアドレス空間に既に割り当てられている場合、この関数は DLL のハンドルを返し、モジュールの参照カウントをインクリメントします。

DLL にエントリ ポイント関数が含まれる場合、オペレーティング システムは、`LoadLibrary` を呼び出したスレッドのコンテキスト内でその関数を呼び出します。 `LoadLibrary` の前回の呼び出しに対応する `FreeLibrary` 関数呼び出しが行われていないために、DLL が既にプロセスにアタッチされている場合は、エントリ ポイント関数は呼び出されません。

使用することお勧めを MFC 拡張 Dll を読み込む MFC アプリケーションで`AfxLoadLibrary`の代わりに`LoadLibrary`です。 `AfxLoadLibrary` を呼び出す前に、`LoadLibrary` でスレッド同期を処理します。 `AfxLoadLibrary` のインターフェイス (関数プロトタイプ) は、`LoadLibrary` と同じです。

Windows が DLL を読み込むことができない場合は、プロセスでエラーからの回復を試みることができます。 たとえば、プロセスがユーザーにエラーを通知して、ユーザーに DLL への別のパスを指定するよう要求できます。

> [!IMPORTANT]  
> Dll の完全パスを指定することを確認してください。 ファイルが読み込まれるときに、現在のディレクトリを最初に検索します。 ファイルのパスを指定していないと、目的のファイルでないファイルが読み込まれる場合があります。 別の方法でこれを防ぐを使用して、 [/DEPENDENTLOADFLAG](../build/reference/dependentloadflag.md)リンカー オプション。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [DLL を暗黙的にリンクする方法](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [リンク方式を使い分け](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [ダイナミック リンク ライブラリの検索順序](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)

- [FreeLibrary と AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)

- [GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>関連項目

- [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)