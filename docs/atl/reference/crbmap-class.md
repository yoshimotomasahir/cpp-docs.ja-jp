---
title: CRBMap クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4ca53db3dc74838592ad0b279ac541d23ad097f
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880347"
---
# <a name="crbmap-class"></a>CRBMap クラス
このクラスは、バイナリ レッド ブラック ツリーを使用して、マップ構造体を表します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
```    
  
#### <a name="parameters"></a>パラメーター  
 *K*  
 キーの要素の型。  
  
 *V*  
 要素の値の型。  
  
 *KTraits*  
 コピーまたは主要な要素を移動するために使用するコードです。 参照してください[CElementTraits クラス](../../atl/reference/celementtraits-class.md)の詳細。  
  
 *VTraits*  
 コピーまたは値の要素を移動するために使用するコードです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRBMap::CRBMap](#crbmap)|コンストラクターです。|  
|[CRBMap:: ~ CRBMap](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRBMap::Lookup](#lookup)|キーまたは値を検索するには、このメソッドを呼び出して、`CRBMap`オブジェクト。|  
|[CRBMap::RemoveKey](#removekey)|要素を削除するには、このメソッドを呼び出して、`CRBMap`キーが指定されたオブジェクト。|  
|[CRBMap::SetAt](#setat)|マップに要素のペアを挿入するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>Remarks  
 `CRBMap` 主な要素と関連付けられた値の順序付き配列を管理する特定の型のマッピングの配列のサポートを提供します。 各キーは、1 つだけ関連付けられている値を持つことができます。 バイナリ ツリーの要素 (キーと値で構成される) が格納されている構造体を使用して、 [CRBMap::SetAt](#setat)メソッド。 使用して要素を削除することができます、 [CRBMap::RemoveKey](#removekey)メソッドで、特定のキー値を持つ要素を削除します。  
  
 ツリーの走査が可能なメソッドで行ったなど[CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition)、 [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext)、および[CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)します。  
  
 *KTraits*と*VTraits*パラメーターは、特性クラスをコピーまたは要素の移動に必要な補足コードが含まれています。  
  
 `CRBMap` 派生[CRBTree](../../atl/reference/crbtree-class.md)、レッド ブラック アルゴリズムを使用してバイナリ ツリーを実装します。 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)キーごとに複数の値が許可されるバリエーションです。 派生すぎる`CRBTree`、そのために多くの機能を共有して`CRBMap`します。  
  
 両方に代替`CRBMap`と`CRBMultiMap`によって提供される、 [CAtlMap](../../atl/reference/catlmap-class.md)クラス。 格納する要素の数が少ない場合は、使用を検討して、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスの代わりにします。  
  
 さまざまなコレクション クラスとその機能とパフォーマンス特性の詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="crbmap"></a>  CRBMap::CRBMap  
 コンストラクターです。  
  
```
explicit CRBMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nBlockSize*  
 ブロック サイズ。  
  
### <a name="remarks"></a>Remarks  
 *NBlockSize*パラメーターは、新しい要素が必要なときに割り当てられたメモリ量の測定単位です。 ブロック サイズの増加はメモリ割り当てルーチンの呼び出しを減らすためがより多くのリソースを使用します。 既定値に、一度に 10 個の要素の領域を割り当てます。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用できるその他の方法についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]  
  
##  <a name="dtor"></a>  CRBMap:: ~ CRBMap  
 デストラクターです。  
  
```
~CRBMap() throw();
```  
  
### <a name="remarks"></a>Remarks  
 割り当てられたリソースを解放します。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用できるその他の方法についてはします。  
  
##  <a name="lookup"></a>  CRBMap::Lookup  
 キーまたは値を検索するには、このメソッドを呼び出して、`CRBMap`オブジェクト。  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 検索する要素を識別するキーを指定します。  
  
 *値*  
 検索する値を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 キーが見つかった場合は true、メソッドの最初のフォームを返します。 2 番目と 3 番目のフォームへのポインターを返す、 [CPair](crbtree-class.md#cpair_class)します。  
  
### <a name="remarks"></a>Remarks  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用できるその他の方法についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]  
  
##  <a name="removekey"></a>  CRBMap::RemoveKey  
 要素を削除するには、このメソッドを呼び出して、`CRBMap`キーが指定されたオブジェクト。  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 削除する要素のペアに対応するキー。  
  
### <a name="return-value"></a>戻り値  
 キーが見つかったと削除された、失敗した場合は false の場合は true を返します。  
  
### <a name="remarks"></a>Remarks  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用できるその他の方法についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]  
  
##  <a name="setat"></a>  CRBMap::SetAt  
 マップに要素のペアを挿入するには、このメソッドを呼び出します。  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 追加するキー値、`CRBMap`オブジェクト。  
  
 *値*  
 追加する値、`CRBMap`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 キー/値要素のペアの位置を返します、`CRBMap`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `SetAt` 一致するキーが見つかった場合は、既存の要素を置き換えます。 キーが見つからない場合は、新しいキー/値ペアが作成されます。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)使用できるその他の方法についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CRBTree クラス](../../atl/reference/crbtree-class.md)   
 [CAtlMap クラス](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap クラス](../../atl/reference/crbmultimap-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
