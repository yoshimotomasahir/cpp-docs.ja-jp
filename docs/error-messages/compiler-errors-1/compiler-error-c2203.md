---
title: コンパイラ エラー C2203 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2203
dev_langs:
- C++
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0cbf64e673c84a60c37bce3ffd51bc7016eb7a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169934"
---
# <a name="compiler-error-c2203"></a>コンパイラ エラー C2203
削除演算子は配列の境界を指定できません  
  
 **/Za** (ANSI) のオプション、`delete`演算子は、配列全体ですがない部分または配列の特定のメンバーを削除できます。  
  
 次の例では、C2203 が生成されます。  
  
```  
// C2203.cpp  
// compile with: /Za  
int main() {  
   int *ar = new int[10];  
   delete [4] ar;   // C2203  
   // try the following line instead  
   // delete [] ar;  
}  
```