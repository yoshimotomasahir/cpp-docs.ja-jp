---
title: コンパイラの警告 (レベル 1) C4552 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4552
dev_langs:
- C++
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3b58d33286163050db533fed00d27abe8903e9f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281129"
---
# <a name="compiler-warning-level-1-c4552"></a>コンパイラの警告 (レベル 1) C4552
'operator': 演算子も何も起こりません。予期される演算子の副作用  
  
 式ステートメントなしの副作用を持つ演算子、式の先頭にある場合、誤りと思われます。  
  
 この警告を無効にするには、かっこで囲まれた式を配置します。  
  
 次の例では、C4552 が生成されます。  
  
```  
// C4552.cpp  
// compile with: /W1  
int main() {  
   int i, j;  
   i + j;   // C4552  
   // try the following line instead  
   // (i + j);  
}  
```