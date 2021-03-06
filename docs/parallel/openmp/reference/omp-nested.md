---
title: OMP_NESTED |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6b51df88ae700f81cf84250cc06ae24c9131fec
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691223"
---
# <a name="ompnested"></a>OMP_NESTED
入れ子になった並列処理が有効かどう、入れ子になった並列処理が有効か無効にしない限り、指定`omp_set_nested`です。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>コメント  
 `OMP_NESTED`で環境変数をオーバーライドすることができます、 [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)関数。  
  
 OpenMP の標準の Visual C 実装では既定値は`OMP_DYNAMIC=FALSE`します。  
  
 詳細については、次を参照してください。 [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)です。  
  
## <a name="example"></a>例  
 次のコマンド セット、`OMP_NESTED`環境変数を TRUE にします。  
  
```  
set OMP_NESTED=TRUE  
```  
  
 次のコマンドの現在の設定を表示する、`OMP_NESTED`環境変数。  
  
```  
set OMP_NESTED  
```  
  
## <a name="see-also"></a>関連項目  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)