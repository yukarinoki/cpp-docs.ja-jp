---
title: '方法: テキスト形式 (C++) でリソース スクリプト ファイルを開く |Microsoft Docs'
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
- resource script files [C++], opening in text format
- .rc files [C++], opening in text format
- rc files [C++], opening in text format
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2c2f73c77e86a2b23213b3b6aabdd0bc85f91586
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317070"
---
# <a name="how-to-open-a-resource-script-file-in-text-format"></a>方法: テキスト形式でリソース スクリプト ファイルを開く

ダイアログ ボックスなどのリソースをそのリソース固有のリソース エディター内で開くことなく、プロジェクトのリソース スクリプト (.rc) ファイルの内容を表示する場合があります。 たとえば、リソース ファイル内のすべてのダイアログ ボックスで文字列を検索する場合に、個別にダイアログ ボックスを開区必要はありません。

> [!NOTE]
> プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

含まれています、テキスト エディターでサポートされているグローバルの操作を実行し、すべてのリソースを表示するテキスト形式で簡単にリソース ファイルを開くことができます。

> [!NOTE]
> リソース エディター直接読み取りません .rc または`resource.h`ファイル。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスと同様に、シンボル以外の情報 (コメントなど) はコンパイル プロセス中に破棄されます。 .aps ファイルと .rc ファイルが一致しなくなると、そのたびに .rc ファイルが再生成されます (たとえば、[保存] を実行すると、リソース エディターによって .rc ファイルと resource.h ファイルが上書きされます)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。 コメントを保持する方法については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。

### <a name="to-open-a-resource-script-file-as-text"></a>テキスト形式でリソース スクリプト ファイルを開くには

1. **ファイル**メニュー**オープン**、 をクリックし、**ファイル。**

2. **ファイルを開く** ダイアログ ボックスで、テキスト形式で表示するリソース スクリプト ファイルに移動します。

3. ファイルを強調表示し、ドロップダウン矢印をクリックして、**オープン**ボタン (ボタンの右側にあります)。

4. 選択**プログラムから開く**ドロップダウン メニューから。

5. **プログラムから開く**ダイアログ ボックスで、をクリックして**ソース コード (テキスト) エディター**します。

6. **として開く**ドロップダウン リストで、**テキスト**します。

   リソースが表示されます、**ソース コード**エディター。

\- または -

1. **ソリューション エクスプ ローラー**、.rc ファイルを右クリックします。

2. ショートカット メニューでは、次のように選択します**プログラムから開く...** を選択し、**ソース コード (テキスト) エディター**します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)  
[リソース エディター](../windows/resource-editors.md)