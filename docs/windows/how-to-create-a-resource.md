---
title: '方法: リソース (C++) の作成します。'
ms.date: 11/04/2016
f1_keywords:
- vs.resourceview.F1
- vc.editors.insertresource
- vc.editors.newcustomresource
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
- resources [C++], viewing
- Resource View window
- resources [C++], adding
- Add Resource dialog box [C++]
- Custom Resource Type dialog box [C++]
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
ms.openlocfilehash: fdf158bab7894497dbcfb147eb2c6e061879be75
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "55764052"
---
# <a name="how-to-create-a-resource-c"></a>方法: リソース (C++) の作成します。

**リソース ビュー**ウィンドウには、プロジェクトに含まれるリソース ファイルが表示されます。 Project1.rc など、最上位のフォルダーを展開すると、その .rc ファイル内にあるリソースの種類が表示されます。 各リソースの種類を展開すると、その種類のリソースが表示されます。

> [!NOTE]
> この情報は、ユニバーサル Windows プラットフォーム アプリでのリソースには適用されません。 詳細については、次を参照してください。[アプリのリソースとリソース管理システム](/windows/uwp/app-resources/)します。

> [!NOTE]
> **リソース ビュー**は Express edition でサポートされていません。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

> [!NOTE]
> プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

**リソース ビュー**ウィンドウを使用して、**リソースの追加**ダイアログ ボックスを C++ の Windows デスクトップ アプリケーション プロジェクトにリソースを追加します。 このダイアログ ボックスには、次のプロパティがあります。

|プロパティ|説明|
|---|---|
|**リソースの種類**|作成するリソースの種類を指定します。<br/><br/>カーソルおよびダイアログ ボックスのリソースのカテゴリを展開すると、さらにリソースを表示できます。 ...\Microsoft Visual Studio でこれらのリソースがある`version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct します。 .Rct ファイルを追加する、このディレクトリに配置する必要がありますまたはする必要がありますを指定する場合、[インクルード パス](../windows/how-to-specify-include-directories-for-resources.md)にします。 これらのファイルのリソースは、該当するカテゴリの第 2 レベルに表示されます。 追加できる .rct ファイルの数にあらかじめ設定された制限はありません。<br/><br/>ツリー コントロールの最上位レベルに表示されるリソースは、Visual Studio に用意されている既定のリソースです。|
|**新規**|選択した型に基づくリソースの作成、**リソースの種類**ボックス。 リソースが適切なエディターで開きます。 たとえば、ダイアログ リソースを作成する場合で開きます、[ダイアログ エディター](../windows/dialog-editor.md)します。|
|**Import**|表示されます、**インポート**できますを移動するリソースにする ダイアログ ボックスは、現在のプロジェクトにインポートします。 ビットマップ、アイコン、カーソル、HTML リソース ファイル、サウンド (.WAV) リソース ファイル、またはカスタム リソース ファイルをインポートできます。|
|**Custom**|開く、**新規カスタム リソース** ダイアログ ボックスのカスタム リソースを作成できます。 カスタム リソースを編集するには、バイナリ エディターを使用する必要があります。|

**新規カスタム リソース** ダイアログ ボックスでは、C++ プロジェクトに新しいカスタム リソースを作成することができます。 このダイアログ ボックスには、次のプロパティがあります。

|プロパティ|説明|
|---|---|
|**リソースの種類**|カスタム リソースの種類の名前を入力するためのテキスト ボックスを提供します。 Visual C は、名前を自動的に大文字を終了すると、**新規カスタム リソース** ダイアログ ボックス。|

新しいリソースを作成するときに Visual C 一意の名前を割り当てる、たとえば、`IDD_Dialog1`します。 関連するリソース エディターまたは [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)でリソースのプロパティを編集することによって、このリソース ID をカスタマイズできます。

リソースを作成するには、新しい既定のリソース (テンプレートに基づいていないリソース)、または後でパターン化リソースとして、[テンプレート](../windows/how-to-use-resource-templates.md)します。

> [!NOTE]
> リソース名または Visual Studio によって予約されている ID を指定しません。 予約済みの名前は DESIGNINFO、HWB、および TEXTINCLUDE、予約済み ID は 255 です。

## <a name="to-open-the-resource-view-window"></a>[リソース ビュー] ウィンドウを開くには

選択**リソース ビュー**上、**ビュー**メニュー。

   \- または -

キーを押して**Ctrl** + **Shift** + **E**します。

> [!TIP]
> 右クリック、**リソース ビュー**をコマンドのショートカット メニューを起動します。 また、タイトル バーをダブルクリックすると、ウィンドウのドッキングやドッキング解除ができます。 タイトル バーを右クリックすると、さらにコマンドが表示され、ウィンドウの動作を制御できます。 詳細については、次を参照してください。 [Windows 管理](/visualstudio/ide/customizing-window-layouts-in-visual-studio)します。

## <a name="to-create-a-new-resource-in-resource-view"></a>リソース ビューでリソースを新規作成するには

1. .Rc ファイルに重点を置いて**リソース ビュー**を選択、**編集**メニュー選択**リソースの追加**(で .rc ファイルを右クリックしてまたは**リソース ビュー**選択**リソースの追加**ショートカット メニューから)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. **リソースの追加** ダイアログ ボックスで、プロジェクトに追加するにはリソースの種類を選択します。

## <a name="to-create-a-new-resource-in-solution-explorer"></a>ソリューション エクスプローラーでリソースを新規作成するには

1. **ソリューション エクスプローラー**でプロジェクト フォルダーを右クリックし、ショートカット メニューの **[追加]**、 **[リソースの追加]** の順にクリックします。

   プロジェクトに .rc ファイルがない場合、この手順は 1 つ作成は。 その後、この手順を繰り返すと、特定のリソースの種類を新しい .rc ファイルに追加できます。

2. **リソースの追加** ダイアログ ボックスで、プロジェクトに追加するにはリソースの種類を選択します。

## <a name="to-create-a-new-resource-in-class-view"></a>クラス ビューでリソースを新規作成するには

1. [クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)クラスを右クリックし、選択、**追加**を選択し、**リソースの追加**ショートカット メニューから。

2. **リソースの追加** ダイアログ ボックスで、プロジェクトに追加するにはリソースの種類を選択します。

## <a name="to-create-a-new-resource-from-the-project-menu"></a>[プロジェクト] メニューからリソースを新規作成するには

**[プロジェクト]** メニューの **[リソースの追加]** を選択します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソース エディター](../windows/resource-editors.md)<br/>
