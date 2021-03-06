---
title: IAxWinHostWindow インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfafe3c59b8b36e95441c7fe269239d7f87111e7
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885855"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow インターフェイス
このインターフェイスは、コントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|ホスト オブジェクトを既存のコントロールをアタッチします。|  
|[CreateControl](#createcontrol)|コントロールを作成し、そのホスト オブジェクトにアタッチします。|  
|[CreateControlEx](#createcontrolex)|コントロールを作成し、ホスト オブジェクトにアタッチします必要に応じて、イベント ハンドラーを設定します。|  
|[QueryControl](#querycontrol)|ホストされるコントロールにインターフェイス ポインターを返します。|  
|[SetExternalDispatch](#setexternaldispatch)|外部の設定`IDispatch`インターフェイス。|  
|[SetExternalUIHandler](#setexternaluihandler)|外部の設定`IDocHostUIHandlerDispatch`インターフェイス。|  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスは、オブジェクトのホスト、ATL の ActiveX コントロールによって公開されます。 作成や、ホストされるコントロールからインターフェイスを取得または Web ブラウザーをホストする場合は、外部のディスパッチ インターフェイスまたは使用するための UI ハンドラーを設定する、ホスト オブジェクトへのコントロールをアタッチするには、このインターフェイスでメソッドを呼び出します。  
  
## <a name="requirements"></a>必要条件  
 このインターフェイスの定義は、次に示すように IDL または C++ では、使用可能です。  
  
|定義の種類|ファイル|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h にも含まれています)|  
  
##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl  
 識別されるウィンドウを使用して、そのホスト オブジェクトを既存の (および前に初期化された) コントロールをアタッチします*hWnd*します。  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnkControl*  
 [in]ポインター、`IUnknown`ホスト オブジェクトにアタッチされるコントロールのインターフェイス。  
  
 *hWnd*  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="createcontrol"></a>  については  
 コントロールを作成し、初期化して、識別されるウィンドウでホスト*hWnd*します。  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpTricsData*  
 [in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) の CLSID、ProgID、URL、または生の HTML にすることができます (付いて**MSHTML:**)。  
  
 *hWnd*  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
 *pStream*  
 [in]コントロールの初期化データを含むストリームのインターフェイス ポインター。 NULL にすることができます。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 このウィンドウは、メッセージをコントロールに反映されることができ、その他のコンテナーの機能は動作できるように、このインターフェイスを公開するホスト オブジェクトをサブクラス化されます。  
  
 このメソッドを呼び出すには、[詳細](#createcontrolex)します。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。 [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)します。  
  
##  <a name="createcontrolex"></a>  詳細  
 ActiveX コントロールを作成、初期化、および指定したウィンドウでホスト[については](#createcontrol)します。  
  
```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpTricsData*  
 [in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) の CLSID、ProgID、URL、または生の HTML にすることができます (付いて**MSHTML:**)。  
  
 *hWnd*  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
 *pStream*  
 [in]コントロールの初期化データを含むストリームのインターフェイス ポインター。 NULL にすることができます。  
  
 *ppUnk*  
 [out]受信するポインターのアドレス、`IUnknown`作成されたコントロールのインターフェイス。 NULL にすることができます。  
  
 *riidAdvise*  
 [in]送信のインターフェイスに含まれるオブジェクトのインターフェイスの識別子です。 Iid_ をすることができます。  
  
 *punkAdvise*  
 [in]ポインター、`IUnknown`で指定された、含まれるオブジェクトの接続ポイントに接続されているシンク オブジェクトのインターフェイス`iidSink`します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 異なり、`CreateControl`メソッド、`CreateControlEx`新しく作成されたコントロールへのインターフェイス ポインターを受け取るし、コントロールによって発生したイベントを受信するために、イベント シンクをセットアップすることもできます。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。[呼び出し](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)します。  
  
##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl  
 ホストされるコントロールによって提供される指定されたインターフェイス ポインターを返します。  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 *riid*  
 [in]要求されているコントロールのインターフェイスの ID。  
  
 *ppvObject*  
 [out]作成されたコントロールの指定したインターフェイスを受信するポインターのアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch  
 格納されているコントロールを使用できる外部のディスパッチ インターフェイスの設定、 [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md)メソッド。  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDisp*  
 [in]ポインター、`IDispatch`インターフェイス。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler  
 外部を設定するには、この関数を呼び出す[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)のためのインターフェイス、`CAxWindow`オブジェクト。  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDisp*  
 [in]ポインター、`IDocHostUIHandlerDispatch`インターフェイス。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 この関数は、ホストのサイト (Web ブラウザー コントロール) などのコントロールで使用、`IDocHostUIHandlerDispatch`インターフェイス。  
  
## <a name="see-also"></a>関連項目  
 [IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









