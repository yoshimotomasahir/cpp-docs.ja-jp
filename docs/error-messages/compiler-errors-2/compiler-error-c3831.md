---
title: コンパイラ エラー C3831 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3831
dev_langs:
- C++
helpviewer_keywords:
- C3831
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47c0295f598b79436d1f892114615473d16275e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268062"
---
# <a name="compiler-error-c3831"></a>コンパイラ エラー C3831
'member': 'class' は、ピン留めしたデータ メンバー、またはピン ポインターを返すメンバー関数を持つことはできません  
  
 [pin_ptr (C + + CLI)](../../windows/pin-ptr-cpp-cli.md)正しく使用されていません。  
  
## <a name="example"></a>例  
 次の例では、C3831 が生成されます。  
  
```  
// C3831a.cpp  
// compile with: /clr  
ref class Y  
{  
public:  
   int i;  
};  
  
ref class X  
{  
   pin_ptr<int> mbr_Y;   // C3831  
   int^ mbr_Y2;   // OK  
};  
  
int main() {  
   Y y;  
   pin_ptr<int> p = &y.i;  
}  
```  
