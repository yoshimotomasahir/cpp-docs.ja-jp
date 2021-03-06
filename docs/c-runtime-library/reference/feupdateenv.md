---
title: feupdateenv | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- feupdateenv
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: HeaderDef
f1_keywords:
- feupdateenv
- fenv/feupdateenv
dev_langs:
- C++
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d88284717aec7a19c936d7ed8d87da96006d7ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397595"
---
# <a name="feupdateenv"></a>feupdateenv

現在発生している浮動小数点例外を保存し、指定した浮動小数点環境状態を復元し、保存されている浮動小数点例外を発生させます。

## <a name="syntax"></a>構文

```C
int feupdateenv(
   const fenv_t* penv
);
```

### <a name="parameters"></a>パラメーター

*penv*<br/>
ポインター、 **fenv_t**オブジェクトとして含まれている浮動小数点環境設定への呼び出しによって[分かって](fegetenv1.md)または[feholdexcept](feholdexcept2.md)です。 また、FE_DFL_ENV マクロを使用して、既定のスタートアップ浮動小数点環境を指定することもできます。

## <a name="return-value"></a>戻り値

すべてのアクションが正常に完了した場合は、0 を返します。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>コメント

**Feupdateenv**関数は、複数のアクションを実行します。 まず、現在発生している浮動小数点例外状態フラグを自動ストレージに格納します。 格納されている値から現在の浮動小数点環境を設定し、 **fenv_t**によって指されるオブジェクト*penv*です。 場合*penv*は**FE_DFL_ENV**が有効なを指していませんまたは**fenv_t**オブジェクト、それ以降の動作は未定義です。 最後に、 **feupdateenv**ローカルに格納された浮動小数点例外を発生させます。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
