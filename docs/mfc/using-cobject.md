---
title: CObject の使い方 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0fab92dddc10a66fe350d343f1fd280ce5c9a50
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027152"
---
# <a name="using-cobject"></a>CObject の使い方
[CObject](../mfc/reference/cobject-class.md)ルート基本クラスが、ほとんどの Microsoft Foundation Class ライブラリ (MFC)。 `CObject`クラスにはシリアル化のサポート、ランタイム クラス情報、オブジェクトの診断出力など、独自のプログラム オブジェクトに組み込むことが必要な多くの便利な機能が含まれています。 クラスを派生させる場合`CObject`、クラスは、これらを悪用できる`CObject`機能します。  
  
## <a name="what-do-you-want-to-do"></a>どうしたいんですか  
  
-   [CObject からクラスを派生します。](../mfc/deriving-a-class-from-cobject.md)  
  
-   [派生クラスに、ランタイム クラス情報、動的な作成、およびシリアル化のサポートを追加します。](../mfc/specifying-levels-of-functionality.md)  
  
-   [ランタイム クラス情報へのアクセス](../mfc/accessing-run-time-class-information.md)  
  
-   [オブジェクトを動的に作成します。](../mfc/dynamic-object-creation.md)  
  
-   [診断のために、オブジェクトのデータをダンプします。](http://msdn.microsoft.com/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   オブジェクトの内部状態の検証 (を参照してください[MFC ASSERT_VALID と cobject::assertvalid](http://msdn.microsoft.com/7654fb75-9e9a-499a-8165-0a96faf2d5e6))  
  
-   [それ自体を永続的ストレージにシリアル化クラスします。](../mfc/serialization-in-mfc.md)  
  
-   一覧を参照してください[CObject よくある質問。](../mfc/cobject-class-frequently-asked-questions.md)  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [CRuntimeClass 構造体](../mfc/reference/cruntimeclass-structure.md)   
 [ファイル](../mfc/files-in-mfc.md)   
 [シリアル化](../mfc/serialization-in-mfc.md)

