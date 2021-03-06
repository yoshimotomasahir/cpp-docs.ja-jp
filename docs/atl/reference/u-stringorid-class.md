---
title: _U_STRINGorID クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
dev_langs:
- C++
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 611fecad210b9297b6c7cd16c83dbd0c6c3e41a8
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886168"
---
# <a name="ustringorid-class"></a>_U_STRINGorID クラス
この引数のアダプター クラスは、リソース名 (LPCTSTRs) またはリソース Id、ID を持つときはマクロを使用して文字列に変換する、呼び出し元を必要とせず、関数に渡される (ついて) のいずれかを使用できます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class _U_STRINGorID
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|コンストラクターです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|リソースの識別子です。|  
  
## <a name="remarks"></a>Remarks  
 このクラスがなどには、Windows リソース管理 API のラッパーを実装するために設計された、 [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042)、 [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072)、および[LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990)関数で、そのまま使用いずれかのリソースの名前または ID 可能性のある LPCTSTR 引数  
  
 クラスは、2 つのコンス トラクター オーバー ロードを定義します: LPCTSTR 引数を受け取るいずれかと UINT 引数を受け取る他。 UINT 引数を持つときはマクロと、クラスの 1 つのデータのメンバーに保存された結果を使用して Windows リソース管理機能と互換性のあるリソースの種類に変換[m_lpstr](#_u_stringorid__m_lpstr)します。 LPCTSTR コンス トラクターの引数は、変換せずに直接格納されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  
  
##  <a name="_u_stringorid__m_lpstr"></a>  _U_STRINGorID::m_lpstr  
 クラスは、パブリック LPCTSTR データ メンバーとしてそのコンス トラクターのいずれかに渡される値を保持します。  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>  _U_STRINGorID::_U_STRINGorID  
 UINT コンス トラクターの引数を持つときはマクロを使用して Windows リソース管理機能と互換性のあるリソースの種類に変換し、クラスの 1 つのデータ メンバーに、結果が格納されている[m_lpstr](#_u_stringorid__m_lpstr)します。  
  
```
_U_STRINGorID(UINT nID);  
_U_STRINGorID(LPCTSTR lpString);
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 リソース id です。  
  
 *lpString*  
 リソースの名前。  
  
### <a name="remarks"></a>Remarks  
 LPCTSTR コンス トラクターの引数は、変換せずに直接格納されます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
