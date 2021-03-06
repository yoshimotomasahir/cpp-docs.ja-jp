---
title: Criticalsection::criticalsection コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d86c80d169cb6d9794f163290c30bf1b2563588b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870898"
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection コンストラクター
ミュー テックス オブジェクトに似ていますが、1 つのプロセスのスレッドのみで使用できる同期オブジェクトを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `spincount`  
 クリティカル セクション オブジェクト用のスピン カウントします。 既定値は 0 です。  
  
## <a name="remarks"></a>コメント  
 クリティカル セクションおよび spincounts の詳細については、次を参照してください。、 **InitializeCriticalSectionAndSpinCount**関数については、Windows API ドキュメントの [同期] セクションでします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [CriticalSection クラス](../windows/criticalsection-class.md)
