---
title: _CxxThrowException | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CxxThrowException
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
apitype: DLLExport
f1_keywords:
- CxxThrowException
- _CxxThrowException
dev_langs:
- C++
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd3ab2994359e99e490422fbb2f11cf28a05d6e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395661"
---
# <a name="cxxthrowexception"></a>_CxxThrowException

例外レコードを作成し、ランタイム環境を呼び出して例画の処理を開始します。

## <a name="syntax"></a>構文

```C
extern "C" void __stdcall _CxxThrowException(
   void* pExceptionObject
   _ThrowInfo* pThrowInfo
);
```

### <a name="parameters"></a>パラメーター

*pExceptionObject*例外を生成するオブジェクト。

*pThrowInfo*例外を処理するために必要な情報です。

## <a name="remarks"></a>コメント

このメソッドは、コンパイラで例外処理に使用されるコンパイラ専用ファイルに含まれています。 このメソッドはコードから直接呼び出さないでください。

## <a name="requirements"></a>要件

**ソース:** Throw.cpp

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
