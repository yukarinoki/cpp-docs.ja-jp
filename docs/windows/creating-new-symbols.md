---
title: '方法: シンボルを作成する (C++)'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.creating
- vc.editors.symbol.managing
- vc.editors.resourcesymbols
- vc.editors.symbol.resource
helpviewer_keywords:
- New Symbol dialog box [C++]
- symbols [C++], creating
- resources [C++], viewing
- resource symbols
- symbols [C++], viewing
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
- resource symbols
- View Use button
- resource editors [C++], resource symbols
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
ms.openlocfilehash: 008d2ab420034e628251c08222bf2e9f723deab1
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504507"
---
# <a name="how-to-create-symbols-c"></a>方法: シンボルを作成する (C++)

新しいプロジェクトを開始するときに、必要なシンボル名をマップしてから、割り当てられるリソースを作成すると便利な場合があります。

> [!NOTE]
> プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [方法: リソースを作成する](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

[ **リソースシンボル** ] ダイアログボックスでは、新しいリソースシンボルの追加、表示されるシンボルの変更、またはシンボルが使用されているソースコード内の場所へのスキップを行うことができます。

このダイアログボックスには、次のプロパティがあります。

|プロパティ|説明|
|--------------------------|------------------------------------------|
|**名前**|シンボルの名前を表示します。<br/><br/>詳細については、「 [シンボル名の制限](./changing-a-symbol-or-symbol-name-id.md)」を参照してください。|
|**Value**|シンボルの数値を表示します。<br/><br/>詳細については、「 [シンボル値の制限](./changing-a-symbol-or-symbol-name-id.md)」を参照してください。|
|**使用中**|シンボルが 1 つ以上のリソースで使用されることを指定する場合にオンにします。<br/><br/>リソースが [ **使用** 方法] ボックスに一覧表示されます。|
|**読み取り専用のシンボルを表示**|読み取り専用のリソースを表示する場合にオンにします。<br/><br/>既定では、[ **リソースシンボル** ] ダイアログボックスには、リソーススクリプトファイル内の変更可能なリソースのみが表示されますが、このオプションを選択すると、変更可能なリソースが太字で表示され、読み取り専用のリソースがプレーンテキストで表示されます。|
|**使用者**|シンボル一覧で選択したシンボルを使用するリソースが表示されます。<br/><br/>特定のリソースのエディターに移動するには、[ **使用** 方法] ボックスでリソースを選択し、[ **表示**] を選択します。|
|**[新規作成]**|[ **新しいシンボル** ] ダイアログボックスを開きます。このダイアログボックスでは、新しいシンボリックリソース識別子の名前と、必要に応じて値を定義できます。|
|**変更**|シンボルの名前または値を変更できる [ **シンボルの変更** ] ダイアログボックスを開きます。<br/><br/>使用中のコントロールまたはリソースのシンボルを変更するには、対応するリソース エディターを使用する必要があります。 詳細については、「 [シンボルの管理](./changing-a-symbol-or-symbol-name-id.md)」を参照してください。|
|**表示**|対応するリソース エディターで、シンボルが含まれたリソースを開きます。|

## <a name="create-symbols"></a>シンボルの作成

### <a name="to-create-a-new-symbol"></a>新しいシンボルを作成するには

1. [ **リソースシンボル** ] ダイアログボックスで、[ **新規作成**] を選択します。

1. [ **名前** ] ボックスにシンボル名を入力します。

1. 割り当てられたシンボル値をそのまま使用するか、[ **値** ] ボックスに新しい値を入力します。

1. [ **OK]** を選択して、新しい記号をシンボルの一覧に追加します。

> [!NOTE]
> 既に存在するシンボルの名前を入力すると、その名前のシンボルが既に定義されていることを示すメッセージ ボックスが表示されます。 同じ名前を持つ複数の記号を定義することはできませんが、同じ数値を使用して異なる記号を定義することはできます。

## <a name="to-view-resource-symbols"></a>リソース シンボルを表示するには

[リソースビュー](how-to-create-a-resource-script-file.md#create-resources)で、 *.rc*ファイルを右クリックし、[リソース**シンボル] を選択し**て、[リソースシンボル **] ダイアログボックス**にリソースシンボルテーブルを表示します。

> [!NOTE]
> 定義済みのシンボルを表示するには、[読み取り専用の **シンボルを表示** する] チェックボックスをオンにします。

### <a name="to-open-the-resource-editor-for-a-given-symbol"></a>指定されたシンボルのリソースエディターを開くには

**リソースシンボル**のシンボルを参照するときは、特定のシンボルの使用方法に関する詳細情報が必要になることがあります。 [ **使用状況の表示** ] ボタンを使用すると、この情報を簡単に取得できます。

1. [ **リソースシンボル** ] ダイアログボックスの [ **名前** ] ボックスで、シンボルを選択します。

1. [ **使用者** ] ボックスで、関心のあるリソースの種類を選択します。

1. [ **ビューの使用** ] ボタンを選択します。

   リソースが適切なエディターに表示されます。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>
[方法: シンボルを管理する](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>
[定義済みのシンボル Id](../windows/predefined-symbol-ids.md)<br/>
