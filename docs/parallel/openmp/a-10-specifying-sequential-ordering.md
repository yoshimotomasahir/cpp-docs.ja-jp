---
title: シーケンシャルな順序を指定する a.10 順番 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48e512a669025403b76b76b49c5bb496b5eacd23
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690079"
---
# <a name="a10---specifying-sequential-ordering"></a>A.10 順番の指定
セクションでは順序付け ([セクション 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 22 ページ上) は並列で行われる仕事からの出力を順番に配置するのに便利です。 次のプログラムを順番にインデックスを出力します。  
  
```  
#pragma omp for ordered schedule(dynamic)  
    for (i=lb; i<ub; i+=st)  
        work(i);  
void work(int k)  
{  
    #pragma omp ordered  
        printf_s(" %d", k);  
}  
```