---
title: コンパイラの警告 (レベル 1) C4097 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4097
dev_langs:
- C++
helpviewer_keywords:
- C4097
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bc91f29d7d6544b2b9f0bfcf84ca5b043b74fe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272049"
---
# <a name="compiler-warning-level-1-c4097"></a>コンパイラの警告 (レベル 1) C4097
プラグマ パラメーターに 'restore' または 'off' が必要です。  
  
 プラグマに無効な値が渡されました。  
  
 次の例では C4097 が生成されます。  
  
```  
// C4097.cpp  
// compile with: /W1  
#pragma runtime_checks("",test)   // C4097  
// try the following line instead  
// #pragma runtime_checks("",off)  
  
int main() {  
}  
```