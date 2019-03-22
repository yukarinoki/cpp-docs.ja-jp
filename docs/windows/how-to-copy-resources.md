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
ms.openlocfilehash: 9867fdf260750d47421e699cdd0d7a58b02ce947
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328624"
---
# <a name="how-to-manage-resources-c"></a>方法: リソース (C++) の管理します。

## <a name="copy-and-edit-resources"></a>コピーとリソースの編集

コピー中に言語またはリソースの条件を変更するか、それらを変更せず、別に 1 つのファイルからリソースをコピーできます。

現在のリソース ファイルを既存のリソースまたは実行可能ファイルからリソースを簡単にコピーできます。 リソースをコピーするには、と同時にリソースが含まれる両方のファイルを開くと別に 1 つのファイルから項目をドラッグまたはコピーして貼り付ける 2 つのファイル。 このメソッドは、リソース スクリプト (.rc) ファイルとリソース テンプレート (.rct) ファイル、および実行可能ファイル (.exe) ファイルとして機能します。

> [!NOTE]
> Visual C には、独自のアプリケーションで使用できるサンプル リソース ファイルが含まれています。 詳細については、次を参照してください[CLIPART:。共通リソース](https://github.com/Microsoft/VCSamples)します。

ドラッグ アンド ドロップ、コピー、切り取り、またはプロジェクト内のリソース ファイル間に貼り付けることはできません (**リソース ビュー**) スタンドアロンの .rc ファイルがドキュメント ウィンドウで開く。 これは、製品の以前のバージョンで実行できます。 プロジェクトの外部に開いている .rc ファイル間でドラッグ アンド ドロップ メソッドのみを使用します。

### <a name="to-copy-resources"></a>リソースをコピーするには

1. 2 つのリソース ファイルをスタンドアロンで開きます。 (を参照してください[リソース スクリプト ファイルを使用して、](how-to-create-a-resource-script-file.md#use-resource-script-files))。 たとえば、開く*Source1.rc*と*Source2.rc*します。

1. 内で最初の .rc ファイルのいずれか。

   - ドラッグ アンド ドロップを使用して、

      1. コピーするリソースを選択します。 たとえば、 *Source1.rc*、 **IDD_DIALOG1**します。

      1. 押しながら、 **Ctrl**キーし、2 番目の .rc ファイルにリソースをドラッグします。 たとえば、ドラッグ**IDD_DIALOG1**から*Source1.rc*に*Source2.rc*します。

         > [!TIP]
         > 保持することがなくリソースをドラッグする、 **Ctrl**キーはコピーすることではなく、リソースが移動します。

   - コピーして貼り付ける方法

      1. リソースを右クリックしてでコピーする (たとえば、 *Source1.rc*) 選択**コピー**。

      1. 貼り付けなど、リソース ファイルを右クリックして (たとえば、 *source2.rc を開きます*) 選択**貼り付けます**します。

> [!NOTE]
> シンボル名または既存のファイル内の値との競合を避けるためには、Visual C が転送されるリソースのシンボル値またはシンボル名や値を変更、新しいファイルをコピーする場合。

リソースのコピー時に、リソースの言語プロパティ、条件プロパティ、またはその両方を変更できます。

- リソースの言語で使用される言語を指定[FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea)参照して、リソースを識別できるようにします。 日本語キーボードでのみ動作する可能性があるアクセラレータや中国語のローカライズされた適切なことはビットマップが構築できるなど、リソースがテキストに関連していない各言語の相違点を設定できます。

- リソースの条件とは、リソースの特定のコピーが使用される条件を識別する定義済みのシンボルです。

言語とリソースの条件でリソースの名前の後にかっこ内に表示されます、**ワークスペース**ウィンドウ。 ここで指定されたリソース`IDD_AboutBox`を使用している`Finnish`、言語およびその条件としては`XX33`:

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>既存のリソースをコピーして、そのリソースの言語または条件を変更するには

*.Rc*ファイルまたは、[リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)ウィンドウで、コピーするリソースを右クリックして**コピーの挿入**します。 次のように設定します。

- **言語**ボックスの一覧で、言語を選択します。

- **条件**ボックスに、条件を入力します。

### <a name="to-edit-resources"></a>リソースを編集するには

マネージ リソース (.resx) ファイルは、XML ファイルです。 マネージ リソース ファイルからプロジェクトに追加すると、**新しい項目の追加** ダイアログ ボックスで、**マネージ リソース エディター**が既定で開きます。

## <a name="import-and-export-resources"></a>インポートおよびエクスポートのリソース

グラフィカル リソース (ビットマップ、アイコン、カーソル、ツール バー)、HTML ファイル、および Visual C++ で使用するためのカスタム リソースをインポートすることができます。 Visual C++ プロジェクトから、同じ種類のファイルを別のファイルにエクスポートして、開発環境の外部で使用することができます。

> [!NOTE]
> アクセラレータ、ダイアログ ボックスに、文字列テーブルなどのリソースの種類のインポートまたはスタンドアロン ファイルの種類とは違うためにエクスポートすることはできません。

### <a name="to-import-a-resource-into-the-resource-script-file"></a>リソース スクリプト ファイルにリソースをインポートするには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)リソースを追加し、選択するリソース スクリプト (.rc) ファイルのノードを右クリックして**インポート**します。

1. 検索し、ビットマップ (.bmp)、アイコン (.ico)、カーソル (.cur)、html ファイル (.htm)、またはインポートするには、その他のファイルのファイル名を選択します。

1. 選択**OK**リソース、リソース スクリプト ファイルを追加します。

> [!NOTE]
> インポート プロセスでは、同じ問題がリソースの種類が選択されていないは機能します。 インポートされたリソースは、そのリソースの種類の適切なノードに自動的に追加されます。

### <a name="to-export-a-resource-for-use-outside-of-visual-c"></a>Visual C の外部で使用するためのリソースをエクスポートするには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)、エクスポートを選択するリソースを右クリックして**エクスポート**します。 現在のファイル名をそのまま使用したり、新しい名前を入力することができます。

1. ファイルを保存し、選択するフォルダーに移動します**エクスポート**します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[方法: リソースの作成](../windows/how-to-create-a-resource-script-file.md)<br/>
[方法: コンパイル時にリソースをインクルードする](../windows/how-to-include-resources-at-compile-time.md)<br/>