---
title: '方法: リソース (C++) の管理します。'
ms.date: 02/14/2019
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
- vc.resvw.resource.changing
- vb.xmldesigner.data
- vs.resvw.resource.importing
- vc.resvw.resource.importing
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
- Language property [C++]
- .resx files [C++], editing
- resource files [C++], editing
- resx files [C++], editing
- resources [C++], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [C++], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
ms.openlocfilehash: 1f176b3fa19374b402039ecca60e690ade5c0cef
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320628"
---
# <a name="how-to-manage-resources-c"></a>方法: リソース (C++) の管理します。

## <a name="copy-resources"></a>リソースのコピー

変更せずに別の 1 つのファイルからのリソースをコピーすることができます、またはコピー中に言語またはリソースの条件を変更することができます。

現在のリソース ファイルを既存のリソースまたは実行可能ファイルからリソースを簡単にコピーできます。 リソースをコピーするには、と同時にリソースが含まれる両方のファイルを開くと別に 1 つのファイルから項目をドラッグまたはコピーして貼り付ける 2 つのファイル。 このメソッドは、リソース スクリプト (.rc) ファイルとリソース テンプレート (.rct) ファイル、および実行可能ファイル (.exe) ファイルとして機能します。

> [!NOTE]
> Visual C には、独自のアプリケーションで使用できるサンプル リソース ファイルが含まれています。 詳細については、次を参照してください[CLIPART:。共通リソース](https://github.com/Microsoft/VCSamples)します。

開いている .rc ファイル間でドラッグ アンド ドロップを使用する[プロジェクトの外部に](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>ドラッグ アンド ドロップ メソッドを使用してファイル間でリソースをコピーするには

1. スタンドアロン両方のリソース ファイルを開きます (詳細については、次を参照してください。[プロジェクト外部で .rc ファイル内のリソースを表示](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md))。 たとえば、開く*Source1.rc*と*Source2.rc*します。

1. 最初の .rc ファイル内でコピーするリソースを選択します。 たとえば、 *Source1.rc*、 **IDD_DIALOG1**します。

1. 押しながら、 **Ctrl**キーし、2 番目の .rc ファイルにリソースをドラッグします。 たとえば、ドラッグ**IDD_DIALOG1**から*Source1.rc*に*Source2.rc*します。

   > [!NOTE]
   > 保持することがなくリソースをドラッグする、 **Ctrl**キーはコピーすることではなく、リソースが移動します。

### <a name="to-copy-resources-using-copy-and-paste"></a>コピーを使用してリソースをコピーして貼り付ける

1. スタンドアロン両方のリソース ファイルを開きます (詳細については、次を参照してください。[プロジェクト外部で .rc ファイル内のリソースを表示](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md))。 たとえば、 *Source1.rc*と*Source2.rc*します。

1. リソースをコピーするソース ファイル内 (たとえば、 *Source1.rc*) でリソースを右クリックし、選択**コピー**ショートカット メニューから。

1. 貼り付けなど、リソース ファイルを右クリックし (たとえば、 *Source2.rc*)。 選択**貼り付け**ショートカット メニューから。

   > [!NOTE]
   > ドラッグ アンド ドロップ、コピー、切り取り、またはプロジェクト内のリソース ファイル間に貼り付けることはできません (**リソース ビュー**) とスタンドアロンの .rc ファイル (ドキュメント ウィンドウで開きます)。 これは、製品の以前のバージョンで実行できます。

   > [!NOTE]
   > シンボル名または既存のファイル内の値との競合を避けるためには、Visual C が転送されるリソースのシンボル値またはシンボル名や値を変更、新しいファイルをコピーする場合。

### <a name="change-the-language-or-condition-of-a-resource-while-copying"></a>コピー中に、言語またはリソースの条件を変更します。

リソースのコピー時に、リソースの言語プロパティ、条件プロパティ、またはその両方を変更できます。

- リソースの言語では、そのリソースで使用する言語のみを識別します。 言語を使用して[FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea)参照して、リソースを識別できるようにします。 (ただし、リソースがテキストに関連していない各言語の相違点を持つことができますが日本語キーボードでのみ動作するアクセラレータや中国語のローカライズされた適切なのみになるビットマップが構築できるなど)。

- リソースの条件とは、リソースの特定のコピーが使用される条件を識別する定義済みのシンボルです。

言語とリソースの条件でリソースの名前の後にかっこ内に表示されます、**ワークスペース**ウィンドウ。 この例で、リソースの名前`IDD_AboutBox`を使用している`Finnish`、言語およびその条件としては`XX33`します。

```cpp
IDD_AboutBox (Finnish - XX33)
```

#### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>既存のリソースをコピーして、そのリソースの言語または条件を変更するには

1. .Rc ファイルまたは、[リソース ビュー](../windows/resource-view-window.md)ウィンドウで、コピーするリソースを右クリックします。

1. 選択**コピーの挿入**ショートカット メニューと、次のセットから。

   - **言語**ボックスの一覧で、言語を選択します。

   - **条件**ボックスに、条件を入力します。

## <a name="edit-resources"></a>リソースを編集します。

マネージ リソース ファイル (.resx) は、XML ファイルです。 マネージ リソース ファイルからプロジェクトに追加すると、**新しい項目の追加** ダイアログ ボックスで、**マネージ リソース エディター**が既定で開きます。

## <a name="import-and-export-resources"></a>インポートおよびエクスポートのリソース

グラフィカル リソース (ビットマップ、アイコン、カーソル、ツール バー)、HTML ファイル、および Visual C++ で使用するためのカスタム リソースをインポートすることができます。 Visual C++ プロジェクトから、同じ種類のファイルを別のファイルにエクスポートして、開発環境の外部で使用することができます。

> [!NOTE]
> アクセラレータ、ダイアログ ボックス、文字列テーブルなどのリソースの種類は、スタンドアロンのファイルの種類ではないため、インポートまたはエクスポートすることはできません。

### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>1 つのリソースを現在のリソース ファイルにインポートするには

1. [リソース ビュー](../windows/resource-view-window.md)、リソース スクリプトのノードを右クリックして (* .rc) ファイルのリソースを追加します。

1. 選択**インポート**ショートカット メニューの します。

1. インポートするビットマップ (.bmp)、アイコン (.ico)、カーソル (.cur)、Html ファイル (.htm)、またはその他のファイルを見つけてそのファイル名を選択します。

1. 選択**OK**で選択したファイルにリソースを追加する**リソース**ビュー。

   > [!NOTE]
   > どの種類のリソースを選択した場合も、インポート プロセスは同じように実行されます。 インポートされたリソースは、そのリソースの種類の適切なノードに自動的に追加されます。

### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>(Visual C++ の外部で使用するために) ビットマップ、アイコン、またはカーソルを別のファイルとしてエクスポートするには

1. **リソース**ビューで、エクスポートするリソースを右クリックします。

1. 選択**エクスポート**ショートカット メニューと現在のファイル名を受け入れるか、新しい名前を入力します。

1. ファイルを保存フォルダーに移動します**エクスポート**します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソースを作成します。](../windows/how-to-create-a-resource-script-file.md)<br/>
[コンパイル時にリソースを含める](../windows/how-to-include-resources-at-compile-time.md)<br/>