---
title: '方法: テキスト形式でリソース スクリプト ファイルを開く |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resource script files, opening in text format
- .rc files, opening in text format
- rc files, opening in text format
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14af857d7727ee8df13a9eb6c438342007252950
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880051"
---
# <a name="how-to-open-a-resource-script-file-in-text-format"></a>方法: テキスト形式でリソース スクリプト ファイルを開く
ダイアログ ボックスなどのリソースをそのリソース固有のリソース エディター内で開くことなく、プロジェクトのリソース スクリプト (.rc) ファイルの内容を表示する場合があります。 たとえば、リソース ファイル内のすべてのダイアログ ボックスで文字列を検索する場合に、個別にダイアログ ボックスを開区必要はありません。  
  
> [!NOTE]
>  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
 含まれているすべてのリソースを表示しでサポートされている全体的な操作を実行するテキスト形式でリソース ファイルを簡単に開くことができます、[テキスト エディター](http://msdn.microsoft.com/en-us/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)です。  
  
> [!NOTE]
>  リソース エディターは、.rc ファイルや resource.h ファイルを直接読み取りません。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスと同様に、シンボル以外の情報 (コメントなど) はコンパイル プロセス中に破棄されます。 .aps ファイルと .rc ファイルが一致しなくなると、そのたびに .rc ファイルが再生成されます (たとえば、[保存] を実行すると、リソース エディターによって .rc ファイルと resource.h ファイルが上書きされます)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。 コメントを保持する方法については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)です。  
  
### <a name="to-open-a-resource-script-file-as-text"></a>テキスト形式でリソース スクリプト ファイルを開くには  
  
1.  **ファイル**メニュー**開く**、順にクリックして**ファイル。**  
  
2.  **ファイルを開く** ダイアログ ボックスで、テキスト形式で表示するリソース スクリプト ファイルに移動します。  
  
3.  ファイルを強調表示し、ドロップダウン矢印をクリックして、**開く**(ボタンの右側にある) ボタンをクリックします。  
  
4.  選択**ファイルを開く**ドロップ ダウン メニューからです。  
  
5.  **ファイルを開く**ダイアログ ボックスで、をクリックして**ソース コード (テキスト) エディター**です。  
  
6.  **として開く**ドロップダウン リストで、**テキスト**です。  
  
     リソースがソース コード エディターで開きます。  
  
 \- または -  
  
1.  **ソリューション エクスプ ローラー**、.rc ファイルを右クリックします。  
  
2.  ショートカット メニューから選択**で開く.** 選択してから、**ソース コード (テキスト) エディター**です。  
  

  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)