---
title: 終了ハンドラーに関する制約 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 969930c3918cdc0d2e38747796279c7135aba5a7
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941341"
---
# <a name="restrictions-on-termination-handlers"></a>終了ハンドラーに関する制約
使用することはできません、 **goto**ステートメントにジャンプ、 **_ _try**ステートメント ブロックまたは **_ _finally**ステートメント ブロックです。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 (の外部にジャンプすることができます、ただし、 **_ _try**ステートメント ブロックです)。また、例外ハンドラーまたは終了ハンドラー内で入れ子ことはできません、 **_ _finally**ブロックします。  
  
 また、終端ハンドラーに割り当てられた一部の種類のコードが生成する結果に問題がある場合があります。したがって、これらは慎重に使用する必要があります。 1 つは、 **goto**の外部にジャンプ ステートメント、 **_ _finally**ステートメント ブロックです。 ブロックが正常終了の一部として実行される場合、特に異常は発生しません。 ただし、システムがスタックをアンワインドしている場合は、そのアンワインドが停止し、異常な終了がなかったかのように現在の関数が制御を得ます。  
  
 A**返す**内のステートメントを **_ _finally**ステートメント ブロックを同じ状況大まかに示します。 終了ハンドラーを含む関数の直前の呼び出し元に制御が戻ります。 システムがスタックをアンワインドしていた場合、このプロセスは停止し、例外が発生しなかったかのようにプログラムが処理されます。  
  
## <a name="see-also"></a>関連項目  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)