---
title: XFORM 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6084882bed6690269fbb926f394159491d22978a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885885"
---
# <a name="xform-structure"></a>XFORM 構造体
`XFORM`構造体は、次の形式。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## <a name="remarks"></a>Remarks  
 `XFORM`構造体は、ページ領域の変換にワールド空間を指定します。 `eDx`と`eDy`メンバーは、水平および垂直方向の変換コンポーネントをそれぞれ指定します。 次の表は、操作によって、他のメンバーの使用方法を示しています。  
  
|操作|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|回転の角度のコサイン|回転の角度のサイン|回転角度のサインを負の値|回転の角度のコサイン|  
|`Scaling`|水平スケーリング コンポーネント|Nothing|Nothing|垂直スケーリング コンポーネント|  
|`Shear`|Nothing|水平方向のプロポーショナル定数|垂直方向のプロポーショナル定数|Nothing|  
|`Reflection`|水平方向の反転コンポーネント|Nothing|Nothing|垂直方向の反転コンポーネント|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

