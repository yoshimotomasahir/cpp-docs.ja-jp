---
title: コンパイラ エラー C3347 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3347
dev_langs:
- C++
helpviewer_keywords:
- C3347
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 961ddc31fbd4b2ac5cac283c949ebb443f0ca855
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253109"
---
# <a name="compiler-error-c3347"></a>コンパイラ エラー C3347
'arg': 必要な引数が属性 idl_module 内で指定されていません  
  
 [idl_module](../../windows/idl-module.md) 属性に必須の引数が渡されていません。  
  
 次の例では C3347 が生成されます。  
  
```  
// C3347.cpp  
// compile with: /c  
[module(name="xx")];  
  
[idl_module(dllname="x")];    // C3347  
// try the following line instead  
// [idl_module(name="test", dllname="x")];  
```