---
title: 致命的なエラー C1076 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1076
dev_langs:
- C++
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38577e59ea874dda99d57297fc8c921f444648c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199486"
---
# <a name="fatal-error-c1076"></a>致命的なエラー C1076
コンパイラの制限 : 内部ヒープの上限に達しました。上限を変更するには /Zm オプションを使用してください。  
  
 このエラーは、シンボルが多すぎるか、テンプレートのインスタンス生成が多すぎることが原因で発生する場合があります。  
  
 このエラーを解決するには、次の方法があります。  
  
1.  使用して、 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)で指定された値に、コンパイラ メモリ制限を設定するオプション、 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)エラー メッセージ。 この値に設定する方法を含む詳細については[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]で「解説」セクションを参照してください[/Zm (指定プリコンパイル済みヘッダーのメモリ割り当て制限)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)です。  
  
2.  64 ビット オペレーティング システムで 32 ビット ホスト コンパイラを使用している場合は、代わりに 64 ビット ホスト コンパイラを使用します。 詳細については、次を参照してください。[する方法: コマンドラインで 64 ビット Visual c ツールセットを有効にする](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)です。  
  
3.  不必要なインクルード ファイルを除去します。  
  
4.  不要なグローバル変数を削除します。これを行うには、たとえば、サイズの大きな配列を宣言する代わりに、メモリを動的に割り当てます。  
  
5.  不要な宣言を削除します。  
  
6.  大きな関数を小さな関数に分割します。  
  
7.  大きなクラスを小さなクラスに分割します。  
  
8.  現在のファイルを小さなファイルに分割します。  
  
 場合の値が指定されたビルドの開始後すぐに C1076 **/Zm**プログラムに対して高すぎる可能性があります。 削減、 **/Zm**値。