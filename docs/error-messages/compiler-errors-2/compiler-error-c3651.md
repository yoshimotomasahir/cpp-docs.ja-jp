---
title: コンパイラ エラー C3651 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3651
dev_langs:
- C++
helpviewer_keywords:
- C3651
ms.assetid: a03e692e-c219-4654-9827-8415cfa5a22d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21b88e306bcd8dd5b76d873fd9ad2e0f5771378a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270643"
---
# <a name="compiler-error-c3651"></a>コンパイラ エラー C3651
'member': 明示的なオーバーライドとして使用することはできません、基底クラスのメンバーである必要があります  
  
 明示的なオーバーライドが指定されましたが、オーバーライドされる関数がの型が基本型ではありませんでした。  
  
 詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)です。  
  
 次の例では、C3651 が生成されます。  
  
```  
// C3651.cpp  
// compile with: /clr /c  
ref class C {  
public:  
   virtual void func2();  
};  
  
ref class Other {  
public:  
   virtual void func();  
};  
  
ref class D : public C {  
public:  
   virtual void func() new sealed = Other::func;   // C3651  
   virtual void func2() new sealed = C::func2;   // OK  
};  
```