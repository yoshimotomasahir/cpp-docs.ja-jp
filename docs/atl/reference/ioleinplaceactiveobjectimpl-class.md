---
title: IOleInPlaceActiveObjectImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1339f41a0764e44f46bed7ad24181ce406998c22
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885602"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl クラス
このクラスは、インプレース コントロールとコンテナー間の通信を支援するメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class IOleInPlaceActiveObjectImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IOleInPlaceActiveObjectImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|状況依存のヘルプを有効にします。 ATL の実装では、E_NOTIMPL を返します。|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|モードレス ダイアログ ボックスを有効にします。 ATL の実装では、S_OK を返します。|  
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|ウィンドウ ハンドルを取得します。|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|コントロールは、コンテナーのドキュメント ウィンドウをアクティブ化または非アクティブ化されたときに通知します。 ATL の実装では、S_OK を返します。|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|コントロールは、コンテナーの最上位レベルのフレーム ウィンドウがアクティブ化または非アクティブ化されたときに通知します。 ATL の実装を返します|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|コントロールに境界線のサイズを変更する必要があることを通知します。 ATL の実装では、S_OK を返します。|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|コンテナーからのメニュー アクセス キーのメッセージを処理します。 ATL の実装では、E_NOTIMPL を返します。|  
  
  
## <a name="remarks"></a>Remarks  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299)インターフェイスは、インプレース コントロールとコンテナー間の通信を支援; たとえば、コントロールとコンテナーのアクティブな状態を通信し、コントロールに通知する必要があるサイズを変更します。自体。 クラス`IOleInPlaceActiveObjectImpl`の既定の実装を提供します。`IOleInPlaceActiveObject`サポートと`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>  IOleInPlaceActiveObjectImpl::ContextSensitiveHelp  
 状況依存のヘルプを有効にします。  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) Windows SDK にします。  
  
##  <a name="enablemodeless"></a>  IOleInPlaceActiveObjectImpl::EnableModeless  
 モードレス ダイアログ ボックスを有効にします。  
  
```
HRESULT EnableModeless(BOOL fEnable);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115) Windows SDK にします。  
  
##  <a name="getwindow"></a>  IOleInPlaceActiveObjectImpl::GetWindow  
 コンテナーは、コントロールのウィンドウ ハンドルを取得するには、この関数を呼び出します。  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Remarks  
 一部のコンテナーは、現在のウィンドウがある場合でも、ウィンドウなしにされているコントロールでは機能しません。 ATL の実装の場合、`CComControl::m_bWasOnceWindowless`データ メンバーは TRUE、E_FAIL を返します。 の場合\* *phwnd*が NULL でない`GetWindow`割り当てます*phwnd*コントロール クラスのデータ メンバーに`m_hWnd`S_OK を返します。  
  
 参照してください[IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) Windows SDK にします。  
  
##  <a name="ondocwindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnDocWindowActivate  
 コントロールは、コンテナーのドキュメント ウィンドウをアクティブ化または非アクティブ化されたときに通知します。  
  
```
HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[::ondocwindowactivate](http://msdn.microsoft.com/library/windows/desktop/ms687281) Windows SDK にします。  
  
##  <a name="onframewindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnFrameWindowActivate  
 コントロールは、コンテナーの最上位レベルのフレーム ウィンドウがアクティブ化または非アクティブ化されたときに通知します。  
  
```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[ioleinplaceactiveobject::onframewindowactivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) Windows SDK にします。  
  
##  <a name="resizeborder"></a>  IOleInPlaceActiveObjectImpl::ResizeBorder  
 コントロールに境界線のサイズを変更する必要があることを通知します。  
  
```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[ioleinplaceactiveobject:](http://msdn.microsoft.com/library/windows/desktop/ms680053) Windows SDK にします。  
  
##  <a name="translateaccelerator"></a>  IOleInPlaceActiveObjectImpl::TranslateAccelerator  
 コンテナーからのメニュー アクセス キーのメッセージを処理します。  
  
```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、次の戻り値をサポートします。  
  
 メッセージが正常に変換された場合は s_ok を返します。  
  
 メッセージに変換されていない場合は s_false を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[ioleinplaceactiveobject::translateaccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)  
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)  
 [クラスの概要](../../atl/atl-class-overview.md)
