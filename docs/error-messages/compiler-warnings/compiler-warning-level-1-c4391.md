---
title: コンパイラの警告 (レベル 1) C4391 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4391
dev_langs:
- C++
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0152d6e04d40e3e0389cf51ba7bdf71de4cd4791
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277869"
---
# <a name="compiler-warning-level-1-c4391"></a>コンパイラの警告 (レベル 1) C4391
'signature': 組み込み関数の不適切な戻り値の型は、'type' が必要です  
  
 コンパイラ組み込み関数の関数宣言では、正しくない戻り値の型がありました。 結果のイメージは正しく動作しない可能性があります。  
  
 この警告を解決するか、宣言を修正してまたは宣言を削除し、単に #include 適切なヘッダー ファイルです。  
  
 次の例では、C4391 が生成されます。  
  
```  
// C4391.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_load_ss(float *p);   // C4391  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```