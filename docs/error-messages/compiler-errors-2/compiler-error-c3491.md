---
title: コンパイラ エラー C3491 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3491
dev_langs:
- C++
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bd856f50f3528b3895e4495215b2e479d8a424b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257294"
---
# <a name="compiler-error-c3491"></a>コンパイラ エラー C3491
'var': 変更できないラムダでは値キャプチャは変更できません  
  
 変更できないラムダ式では、値によってキャプチャされる変数の値を変更できません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   `mutable` キーワードでラムダ式を宣言します。または、  
  
-   ラムダ式のキャプチャ リストへの参照によって変数を渡します。  
  
## <a name="example"></a>例  
 次の例では、変更できないラムダ式の本体がキャプチャ変数 `m`を変更するため、C3491 が生成されます。  
  
```  
// C3491a.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) { m = n; }(99); // C3491  
}  
```  
  
## <a name="example"></a>例  
 次の例では、ラムダ式を `mutable` キーワードで宣言することで C3491 を解決しています。  
  
```  
// C3491b.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) mutable { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)