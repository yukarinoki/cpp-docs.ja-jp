---
title: '方法: リソースのコピー (C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
- vc.resvw.resource.changing
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
- Language property [C++]
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
ms.openlocfilehash: 772c9b905d4cb0c4e2ccab9ec51aa02860b2db32
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849662"
---
# <a name="how-to-copy-resources-c"></a>方法: リソースのコピー (C++)

変更せずに別の 1 つのファイルからのリソースをコピーすることができます、またはコピー中に言語またはリソースの条件を変更することができます。

現在のリソース ファイルを既存のリソースまたは実行可能ファイルからリソースを簡単にコピーできます。 リソースをコピーするには、と同時にリソースが含まれる両方のファイルを開くと別に 1 つのファイルから項目をドラッグまたはコピーして貼り付ける 2 つのファイル。 このメソッドは、リソース スクリプト (.rc) ファイルとリソース テンプレート (.rct) ファイル、および実行可能ファイル (.exe) ファイルとして機能します。

> [!NOTE]
> Visual C には、独自のアプリケーションで使用できるサンプル リソース ファイルが含まれています。 詳細については、次を参照してください[CLIPART:。共通リソース](https://github.com/Microsoft/VCSamples)します。

開いている .rc ファイル間でドラッグ アンド ドロップを使用する[プロジェクトの外部に](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

## <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>ドラッグ アンド ドロップ メソッドを使用してファイル間でリソースをコピーするには

1. スタンドアロン両方のリソース ファイルを開きます (詳細については、次を参照してください。 [、.rc ファイルの外部のプロジェクトでリソースを表示する](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md))。 たとえば、Source1.rc と Source2.rc を開きます。

1. 最初の .rc ファイル内でコピーするリソースを選択します。 たとえば、 `Source1.rc`、 **IDD_DIALOG1**します。

1. 押しながら、 **Ctrl**キーし、2 番目の .rc ファイルにリソースをドラッグします。 たとえば、ドラッグ**IDD_DIALOG1**から`Source1.rc`に`Source2.rc`します。

   > [!NOTE]
   > 保持することがなくリソースをドラッグする、 **Ctrl**キーはコピーすることではなく、リソースが移動します。

## <a name="to-copy-resources-using-copy-and-paste"></a>コピーを使用してリソースをコピーして貼り付ける

1. スタンドアロン両方のリソース ファイルを開きます (詳細については、次を参照してください。 [、.rc ファイルの外部のプロジェクトでリソースを表示する](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md))。 たとえば、Source1.rc と source2.rc を開きます。

1. リソースをコピーするソース ファイル内 (たとえば、 `Source1.rc`) でリソースを右クリックし、選択**コピー**ショートカット メニューから。

1. 貼り付けなど、リソース ファイルを右クリックし (たとえば、 `Source2.rc`)。 選択**貼り付け**ショートカット メニューから。

   > [!NOTE]
   > ドラッグ アンド ドロップ、コピー、切り取り、またはプロジェクト内のリソース ファイル間に貼り付けることはできません (**リソース ビュー**) とスタンドアロンの .rc ファイル (ドキュメント ウィンドウで開きます)。 これは、製品の以前のバージョンで実行できます。

   > [!NOTE]
   > シンボル名または既存のファイル内の値との競合を避けるためには、Visual C が転送されるリソースのシンボル値またはシンボル名や値を変更、新しいファイルをコピーする場合。

## <a name="to-change-the-language-or-condition-of-a-resource-while-copying-c"></a>(C++) のコピー中に、言語またはリソースの条件を変更するには

リソースのコピー時に、リソースの言語プロパティ、条件プロパティ、またはその両方を変更できます。

- リソースの言語では、そのリソースで使用する言語のみを識別します。 言語を使用して[FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea)参照して、リソースを識別できるようにします。 (ただし、リソースがテキストに関連していない各言語の相違点を持つことができますが日本語キーボードでのみ動作するアクセラレータや中国語のローカライズされた適切なのみになるビットマップが構築できるなど)。

- リソースの条件とは、リソースの特定のコピーが使用される条件を識別する定義済みのシンボルです。

リソースの言語と条件は、[ワークスペース] ウィンドウで、リソース名の後に、かっこで囲んで表示されます。 この例で、リソース idd_aboutbox が言語のとしてフィンランド語を使用して、条件が XX33 します。

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>既存のリソースをコピーして、そのリソースの言語または条件を変更するには

1. .Rc ファイルまたは、[リソース ビュー](../windows/resource-view-window.md)ウィンドウで、コピーするリソースを右クリックします。

1. 選択**コピーの挿入**ショートカット メニューから。

1. **リソース コピーの挿入** ダイアログ ボックス。

   - **言語**ボックスの一覧で、言語を選択します。

   - **条件**ボックスに、条件を入力します。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソース エディター](../windows/resource-editors.md)<br/>
[方法: プロジェクトの外側で (スタンドアロンで) リソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
