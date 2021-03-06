---
title: CComAutoDeleteCriticalSection クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b90afb9ae47ced33c331aef988489b567b1078b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879903"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection クラス
このクラスは、取得およびクリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Remarks  
 `CComAutoDeleteCriticalSection` クラスから派生[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)します。 ただし、`CComAutoDeleteCriticalSection`オーバーライド、[用語](ccomsafedeletecriticalsection-class.md#term)メソッドを**プライベート**アクセスで、強制的にのみこのクラスのインスタンス スコープ外に出るまたは明示的に削除されたときから発生する内部メモリ クリーンアップメモリ。  

  
 このクラスは、その基本クラスを追加のメソッドを導入しないします。 参照してください[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)と[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クリティカル セクションのヘルパー クラスの詳細についてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcore.h  
  
## <a name="see-also"></a>関連項目  
 [CComSafeDeleteCriticalSection クラス](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
