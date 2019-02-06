---
title: リソース シンボル (C++) の表示
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.managing
- vc.editors.resourcesymbols
helpviewer_keywords:
- resources [C++], viewing
- resource symbols
- symbols [C++], viewing
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
ms.assetid: 4bcc06d9-7d36-486a-8a37-71da0541643c
ms.openlocfilehash: e61269261fc9172288f1edf58419009178c755d9
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763974"
---
# <a name="viewing-resource-symbols"></a>リソース シンボルの表示

**リソース シンボル**C++ ダイアログ ボックスでは、新しいリソース シンボルの追加、シンボルが表示されます、またはシンボルが使用中は、ソース コード内の場所へのスキップを変更することができます。

ダイアログ ボックスには、次のプロパティが含まれています。

|プロパティ|説明|
|---|---|
|**Name**|シンボルの名前を表示します。 詳細については、次を参照してください。[シンボル名の制限](../windows/symbol-name-restrictions.md)します。|
|**[値]**|シンボルの数値を表示します。 詳細については、次を参照してください。[シンボル値の制限](../windows/symbol-value-restrictions.md)します。|
|**使用中**|シンボルが 1 つ以上のリソースで使用されることを指定する場合にオンにします。 リソースの一覧が [次のリソースで使用] ボックスに表示されます。|
|**読み取り専用のシンボルを表示します。**|読み取り専用のリソースを表示する場合にオンにします。 既定で、**リソース シンボル** ダイアログ ボックスにリソース スクリプト ファイルで変更可能なリソースのみが表示されますが、このオプションを選択すると、変更可能なリソースは太字で表示されます。 および読み取り専用のリソースはプレーン テキストで表示されます。|
|**使用されます。**|シンボル一覧で選択したシンボルを使用するリソースが表示されます。 特定のリソース エディターに移動するでリソースを選択します。、**使用者**ボックスと [] をクリック**ビュー使用**。 詳細については、次を参照してください。[特定のシンボル用のリソース エディターを開く](../windows/opening-the-resource-editor-for-a-given-symbol.md)します。|
|**新規**|開く、**新しいシンボル** ダイアログ ボックスで、名前を定義することができ、必要に応じて、新しいシンボル リソース識別子の値。 詳細については、次を参照してください。[シンボルの新規作成](../windows/creating-new-symbols.md)です。|
|**変更**|開く、**シンボルの変更** ダイアログ ボックスで、名前またはシンボルの値を変更することができます。 使用中のコントロールまたはリソースのシンボルを変更するには、対応するリソース エディターを使用する必要があります。 詳細については、次を参照してください。[未使用のシンボルを変更する](../windows/changing-unassigned-symbols.md)します。|
|**ビューの使用**|対応するリソース エディターで、シンボルが含まれたリソースを開きます。 詳細については、次を参照してください。[特定のシンボル用のリソース エディターを開く](../windows/opening-the-resource-editor-for-a-given-symbol.md)します。|

## <a name="to-view-resource-symbols"></a>リソース シンボルを表示するには

1. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックします。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. 選択**リソース シンボル**リソース シンボル テーブルを表示するショートカット メニューから、**リソース シンボル** ダイアログ ボックス。

   > [!NOTE]
   > 定義済みのシンボルを表示するには、確認、**読み取り専用のシンボルを表示**チェック ボックスをオンします。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[シンボル:リソース識別子](../windows/symbols-resource-identifiers.md)