---
title: 3.1.2 omp_get_num_threads 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df01d571b67ff6d252d85128fcc8c1d26a6e94a9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687440"
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads 関数
**Omp_get_num_threads**関数現在を返しますスレッドの数、並列領域の呼び出し元を実行するチームにします。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_num_threads(void);  
```  
  
 **Num_threads**句、 **omp_set_num_threads**関数、および**OMP_NUM_THREADS**環境変数は、チーム内のスレッドの数を制御します。  
  
 スレッドの数が設定されていない場合に明示的にユーザーが、既定値は、実装定義します。 この関数に、最も近い外側にあるバインド**並列**ディレクティブです。 呼び出された場合、プログラムのシリアル部分から、またはシリアル化される入れ子になった並列領域から、この関数は 1 を返します。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **OMP_NUM_THREADS**環境変数を参照してください[セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48 ページ。  
  
-   **num_threads**句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **並列**構築を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。