---
title: コンパイラ エラー C2612 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2612
dev_langs:
- C++
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88053cde81e7eea8bc9e9280cf235d5eccc6704
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226949"
---
# <a name="compiler-error-c2612"></a>コンパイラ エラー C2612
末尾の 'char' ベース/メンバー初期化子リストについています。  
  
 最後の基底クラスまたは初期化子リスト内のメンバーの後に文字が表示されます。  
  
 次の例では、C2612 が生成されます。  
  
```  
// C2612.cpp  
class A {  
public:  
   int i;  
   A( int ia ) : i( ia ) + {};   // C2612  
};  
```