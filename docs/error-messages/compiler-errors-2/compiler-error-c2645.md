---
title: コンパイラ エラー C2645 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2645
dev_langs:
- C++
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0330f9f678da58648c2fd445f7a291b02c167a89
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229149"
---
# <a name="compiler-error-c2645"></a>コンパイラ エラー C2645
メンバーへのポインターの修飾名がない (見つかった ':: *')  
  
 メンバーへのポインターの宣言は、クラスを指定していません。  
  
 次の例では、C2645 が生成されます。  
  
```  
// C2645.cpp  
class A {};  
int main() {  
   int B::* bp;   // C2645 B not defined  
   int A::* ap;   // OK  
}  
```