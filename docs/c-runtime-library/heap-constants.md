---
title: ヒープ定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
dev_langs:
- C++
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25118792500d679d243f55e5d87e62a4994eaa0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389931"
---
# <a name="heap-constants"></a>ヒープ定数
## <a name="syntax"></a>構文  
  
```  
  
#include <malloc.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 これらの定数は、ヒープの状態を示す戻り値を提供します。  
  
|定数|説明|  
|--------------|-------------|  
|`_HEAPBADBEGIN`|初期ヘッダー情報が見つからないか無効です。|  
|`_HEAPBADNODE`|不適切なノードが検出されたか、ヒープが破損しています。|  
|`_HEAPBADPTR`|**_HEAPINFO** 構造体の **_pentry** フィールドに、ヒープへの有効なポインターが含まれていません (`_heapwalk` ルーチンのみ)。|  
|`_HEAPEMPTY`|ヒープが初期化されていません。|  
|`_HEAPEND`|ヒープの末尾に正常に到達しました (`_heapwalk` ルーチンのみ)。|  
|`_HEAPOK`|ヒープに一貫性があります (`_heapset` ルーチンと `_heapchk` ルーチンのみ)。 これまでのところエラーはありません。**_HEAPINFO** 構造体に、次のエントリに関する情報が含まれています (`_heapwalk` ルーチンのみ)。|  
  
## <a name="see-also"></a>参照  
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)