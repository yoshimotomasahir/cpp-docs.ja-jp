---
title: コンパイラ エラー C3283 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3283
dev_langs:
- C++
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bc23270d70a2fec1c0ac9cc5f6b96541085cfc6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249105"
---
# <a name="compiler-error-c3283"></a>コンパイラ エラー C3283
'type': インターフェイスにインスタンス コンストラクターを含めることはできません  
  
 CLR [インターフェイス](../../windows/interface-class-cpp-component-extensions.md) にインスタンス コンストラクターを含めることはできません。  静的コンストラクターが許可されます。  
  
 次の例では C3283 が生成されます。  
  
```  
// C3283.cpp  
// compile with: /clr  
interface class I {  
   I();   // C3283  
};  
```  
  
 考えられる解決方法:  
  
```  
// C3283b.cpp  
// compile with: /clr /c  
interface class I {  
   static I(){}  
};  
```