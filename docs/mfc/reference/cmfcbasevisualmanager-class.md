---
title: CMFCBaseVisualManager クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7b21651bdab6bf2e4603a8fa012480a6201e34b
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336224"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager クラス
派生のビジュアル マネージャーと Windows テーマ API の間のレイヤー。  
  
 `CMFCBaseVisualManager` 可能な場合、UxTheme.dll を読み込み、Windows テーマ API メソッドへのアクセスを管理します。  
  
 このクラスは内部でのみ使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|`CMFCBaseVisualManager` オブジェクトを構築して初期化します。|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|現在の Windows テーマを使用して、チェック ボックス コントロールを描画します。|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|現在の Windows テーマを使用してコンボ ボックスの枠線を描画します。|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|現在の Windows テーマを使用してコンボ ボックス ドロップダウン ボタンを描画します。|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|現在の Windows テーマを使用してプッシュ ボタンを描画します。|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|現在の Windows テーマを使用して、オプション ボタン コントロールを描画します。|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|ステータス バー コントロールに進行状況バーを描画します ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) 現在の Windows テーマを使用します。|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|現在の Windows テーマを使用して、rebar コントロールの背景を塗りつぶします。|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|現在の Windows テーマを取得します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|呼び出し`CloseThemeData`で取得したすべてのハンドルの`UpdateSystemColors`します。|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|呼び出し`OpenThemeData`さまざまなコントロールを描画するためのハンドルを取得する: windows、ツールバー、ボタン、およびなど。|  
  
## <a name="remarks"></a>Remarks  
 このクラスのオブジェクトを直接インスタンス化する必要はありません。  
  
 すべてのビジュアル マネージャーの基本クラスであるため、呼び出すだけで済みます[CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)、現在 Visual マネージャーへのポインターを取得およびのメソッドにアクセス`CMFCBaseVisualManager`そのポインターを使用します。 ただし、現在の Windows テーマを使用してコントロールを表示する場合は、なりますを使用する方がよい、`CMFCVisualManagerWindows`インターフェイス。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes  
 呼び出し`CloseThemeData`で取得したすべてのハンドルの`UpdateSystemColors`します。  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>Remarks  
 内部使用のみ。  
  
##  <a name="cmfcbasevisualmanager"></a>  CMFCBaseVisualManager::CMFCBaseVisualManager  
 `CMFCBaseVisualManager` オブジェクトを構築して初期化します。  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="drawcheckbox"></a>  CMFCBaseVisualManager::DrawCheckBox  
 現在の Windows テーマを使用して、チェック ボックス コントロールを描画します。  
  
```  
virtual BOOL DrawCheckBox(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    int nState,   
    BOOL bEnabled,   
    BOOL bPressed);

);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター  
  
 [in]*rect*  
 チェック ボックスの外接する四角形。  
  
 [in]*bHighlighted*  
 チェック ボックスが強調表示されているかどうかを指定します。  
  
 [in]*状態*  
 0 のチェックの通常のチェックを行わない、1  
  
 混合で通常の 2。  
  
 [in]*bEnabled*  
 チェック ボックスが有効になっているかどうかを指定します。  
  
 [in]*bPressed*  
 チェック ボックスが押されたかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 テーマの API が有効な場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 値*状態*次のチェック ボックスのスタイルに対応しています。  
  
|状態|チェック ボックスのスタイル|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder  
 現在の Windows テーマを使用してコンボ ボックスの枠線を描画します。  
  
```  
virtual BOOL DrawComboBorder(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
 [in]*rect*  
 コンボ ボックスの枠線の外接する四角形。  
  
 [in]*bDisabled*  
 コンボ ボックスの枠線が無効になっているかどうかを指定します。  
  
 [in]*bIsDropped*  
 コンボ ボックスの枠線が削除されるかどうかを指定します。  
  
 [in]*bIsHighlighted*  
 コンボ ボックスの枠線が強調表示されているかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 テーマの API が有効な場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="drawcombodropbutton"></a>  CMFCBaseVisualManager::DrawComboDropButton  
 現在の Windows テーマを使用してコンボ ボックス ドロップダウン ボタンを描画します。  
  
```  
virtual BOOL DrawComboDropButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*pDC*|デバイス コンテキストへのポインター。|  
|[in]*rect*|コンボ ボックスのドロップダウン ボタンの外接する四角形。|  
|[in]*bDisabled*|コンボ ボックスのドロップダウン ボタンが無効になっているかどうかを指定します。|  
|[in]*bIsDropped*|コンボ ボックスのドロップダウン ボタンが削除されるかどうかを指定します。|  
|[in]*bIsHighlighted*|コンボ ボックスのドロップダウン ボタンが強調表示されているかどうかを指定します。|  
  
### <a name="return-value"></a>戻り値  
 テーマの API が有効な場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton  
 現在の Windows テーマを使用してプッシュ ボタンを描画します。  
  
```  
virtual BOOL DrawPushButton(
    CDC* pDC,   
    CRect rect,   
    CMFCButton* pButton,   
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
 [in]*rect*  
 プッシュ ボタンの外接する四角形。  
  
 [in]*pButton*  
 ポインター、 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)を描画するオブジェクト。  
  
 [in]*uiState*  
 無視されます。 状態がから取得した*pButton*します。  
  
### <a name="return-value"></a>戻り値  
 テーマの API が有効な場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="drawradiobutton"></a>  CMFCBaseVisualManager::DrawRadioButton  
 現在の Windows テーマを使用して、オプション ボタン コントロールを描画します。  
  
```  
virtual BOOL DrawRadioButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    BOOL bChecked,   
    BOOL bEnabled,   
    BOOL bPressed);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
 [in]*rect*  
 オプション ボタンの外接する四角形。  
  
 [in]*bHighlighted*  
 ラジオ ボタンが強調表示されているかどうかを指定します。  
  
 [in]*bChecked*  
 ラジオ ボタンがオンになっているかどうかを指定します。  
  
 [in]*bEnabled*  
 ラジオ ボタンが有効になっているかどうかを指定します。  
  
 [in]*bPressed*  
 ラジオ ボタンが押されたかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 テーマの API が有効な場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress  
 ステータス バー コントロールに進行状況バーを描画します ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) 現在の Windows テーマを使用します。  
  
```  
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,   
    CMFCStatusBar* pStatusBar,   
    CRect rectProgress,   
    int nProgressTotal,   
    int nProgressCurr,  
    COLORREF clrBar,   
    COLORREF clrProgressBarDest,   
    COLORREF clrProgressText,   
    BOOL bProgressText);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
 [in]*pStatusBar*  
 ステータス バーへのポインター。 この値は無視されます。  
  
 [in]*rectProgress*  
 外接する四角形で進行状況バー *pDC*座標。  
  
 [in]*nProgressTotal*  
 進行状況の合計値。  
  
 [in]*nProgressCurr*  
 現在の進行状況の値。  
  
 [in]*clrBar*  
 開始色。 `CMFCBaseVisualManager` これは無視されます。 派生クラスを色のグラデーションを使用できます。  
  
 [in]*clrProgressBarDest*  
 最後の色。 `CMFCBaseVisualManager` これは無視されます。 派生クラスを色のグラデーションを使用できます。  
  
 [in]*clrProgressText*  
 進行中テキストの色。 `CMFCBaseVisualManager` これは無視されます。 テキストの色がによって定義されている`afxGlobalData.clrBtnText`します。  
  
 [in]*bProgressText*  
 進行中テキストを表示するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 テーマの API が有効な場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane  
 現在の Windows テーマを使用して、rebar コントロールの背景を塗りつぶします。  
  
```  
virtual void FillReBarPane(
    CDC* pDC,   
    CBasePane* pBar,   
    CRect rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
 [in]*pBar*  
 背景を描画するウィンドウへのポインター。  
  
 [in]*rectClient*  
 格納する領域の外接する四角形。  
  
### <a name="return-value"></a>戻り値  
 テーマの API が有効な場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme  
 現在の Windows テーマを取得します。  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されている Windows テーマの色。 次の列挙値のいずれかを指定できます。  
  
- `WinXpTheme_None` -有効になっているテーマはありません。  
  
- `WinXpTheme_NonStandard` -(つまり、次の一覧から [なし] が、テーマが選択されている) 非標準のテーマを選択します。  
  
- `WinXpTheme_Blue` -青のテーマ (Luna)。  
  
- `WinXpTheme_Olive` -オリーブのテーマ。  
  
- `WinXpTheme_Silver` -シルバーのテーマ。  
  
##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors  
 呼び出し`OpenThemeData`さまざまなコントロールを描画するためのハンドルを取得する: windows、ツールバー、ボタン、およびなど。  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>Remarks  
 内部使用のみ。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
