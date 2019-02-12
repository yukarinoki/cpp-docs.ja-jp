---
title: リソース ファイル (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- resources [C++]
- .rc files [C++]
- resource files [C++]
- resource script files [C++]
- resource script files [C++], Win-32 based applications
- resource script files [C++], files updated when editing resources
- resources [C++], types of resource files
- rct files [C++]
- rc files [C++]
- resource files [C++], types of
- .rct files [C++]
- resource script files [C++], unsupported types
- manifest resources [C++]
- resources [C++], manifest
- resources [C++], opening
- file types [C++], for resources
- resources [C++], editing
- files [C++], editable types
- resource editing
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
ms.openlocfilehash: 65500644b70841f372edcc6911edefc6c7b9f432
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152691"
---
# <a name="resource-files-c"></a>リソース ファイル (C++)

> [!NOTE]
> これは Windows デスクトップ アプリケーションだけに適用できます。 ユニバーサル Windows プラットフォーム アプリでのリソースについては、次を参照してください。[アプリ リソースの定義](/windows/uwp/app-resources/)します。
>
> マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。
>
> .NET プログラミング言語のプロジェクトでは、リソース スクリプト ファイルは使用しないため、 **ソリューション エクスプローラー**」をご覧ください。 [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージド プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

"リソース ファイル" という用語は、次のようなさまざまな種類のファイルを示します。

- プログラムのリソース スクリプト (.rc) ファイル。

- リソース テンプレート (.rct) ファイル。

- ビットマップ、アイコン、カーソル ファイルなど、スタンドアロン ファイルとして存在し、.rc ファイルから参照される個別のリソース。

- Resource.h など、開発環境で生成され、.rc ファイルから参照されるヘッダー ファイル。

リソースにも含ま[他のファイルの種類](../windows/editable-file-types-for-resources.md).exe、.dll、.res ファイルなどです。 現在のプロジェクトの一部ではないものと、プロジェクト内でリソースとリソース ファイルを使用できます。 Visual Studio の開発環境で作成されていないリソース ファイルを操作することもできます。 たとえば、次のように操作できます。

- 入れ子になっていて、条件付きでインクルードされるリソース ファイルの操作。

- 既存のリソースの更新、または Visual C++ 形式への変換。

- グラフィック リソースを現在のリソース ファイルとの間でインポートまたはエクスポートする。

- 開発環境では変更できない共有または読み取り専用識別子 (シンボル) のインクルード。

- 実行可能ファイル (.exe) ファイルの編集を必要としない (または編集することはできません) 中にいくつかのプロジェクト間の共有リソースなど、現在のプロジェクトにリソースが含まれます。

- 開発環境でサポートされていない種類のリソースのインクルード。

次の種類のファイルを開くし、格納されているリソースを編集できます。

|ファイル名|説明|
|---------------|-----------------|
|.rc|リソース スクリプト ファイル。|
|.rct|リソース テンプレート ファイル。|
|.res|リソース ファイル。|
|.resx|マネージド リソース ファイル。|
|.exe|実行可能ファイル。|
|.dll|ダイナミック リンク ライブラリ ファイル。|
|.bmp、.ico、.dib、.cur|ビットマップ、アイコン、ツール バー、カーソルのファイル。|

Visual Studio 環境では、連携して、リソース編集セッション中に次の表に示したファイルに影響を与えます。

|ファイル名|説明|
|---------------|-----------------|
|Resource.h|開発環境で生成されるヘッダー ファイル。シンボル定義が含まれます。 (このファイルはソース管理に含めます。)|
|Filename.aps|高速読み込みに使用される、現在のリソース スクリプト ファイルのバイナリ バージョン。<br /><br /> リソース エディターでは、.rc や resource.h ファイルを直接読み取るはありません。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスでは、コンパイル プロセス中にシンボリック (たとえば、コメントなど) でない情報が破棄されます。 .aps ファイルと .rc ファイルが同期しなくなると、そのたびに .rc ファイルが再生成されます (たとえば、[保存] を実行すると、リソース エディターによって .rc ファイルと resource.h ファイルが上書きされます)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。 コメントを保持する方法については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。 (通常は、するべきではない .aps ファイルに含めるソース管理。)|
|.rc|現在のプロジェクト内のリソース用のスクリプトを格納するリソース スクリプト ファイル。 このファイルは、保存するたびに .aps ファイルで上書きされます。 (このファイルはソース管理に含めます。)|

このセクションでは方法。

- [リソースを作成します。](../windows/how-to-create-a-resource-script-file.md)

- [リソースを管理します。](../windows/how-to-copy-resources.md)

- [コンパイル時にリソースを含める](../windows/how-to-include-resources-at-compile-time.md)

## <a name="manifest-resources"></a>マニフェスト リソース

C++ デスクトップ プロジェクトでは、マニフェスト リソースは、アプリケーションが使用する依存関係を記述する XML ファイルです。 たとえば Visual Studio では、MFC ウィザードで生成されたマニフェスト ファイルで、アプリケーションがバージョン 5.0 と 6.0 のどちらの Windows コモン コントロール DLL を使用するかを定義します。

```xml
<description>Your app description here</description>
<dependency>
    <dependentAssembly>
        <assemblyIdentity
            type="win32"
            name="Microsoft.Windows.Common-Controls"
            version="6.0.0.0"
            processorArchitecture="X86"
            publicKeyToken="6595b64144ccf1df"
            language="*"
        />
    </dependentAssembly>
</dependency>
```

Windows XP または Windows Vista アプリケーションでは、マニフェスト リソースだけでなくことを指定、アプリケーション、上記のように、v6.0 Windows コモン コントロールの最新バージョンを使用してもサポートしています、 [Syslink コントロール](/windows/desktop/Controls/syslink-overview)します。

バージョンを表示し、マニフェスト リソースに含まれる情報の入力には、XML ビューアーで、または Visual Studio テキスト エディターでファイルを開くことができます。 マニフェスト リソースを [リソース ビュー](../windows/resource-view-window.md)から開くと、リソースはバイナリ形式で表示されます。 マニフェスト リソースの内容を見やすい形式で表示するからリソースを開く必要があります**ソリューション エクスプ ローラー**します。

マニフェスト リソースを開くには、次の手順からを選択します。

- テキスト エディターでプロジェクトを開いての**ソリューション エクスプ ローラー**、展開、**リソース ファイル**フォルダー .manifest ファイルをダブルクリックします。

- 別のエディターで**ソリューション エクスプ ローラー**.manifest ファイルを右クリックして選択**プログラムから開く.** ショートカット メニューから。 **プログラムから開く** ダイアログ ボックスで、使用し、選択するエディターを指定**オープン**します。

> [!NOTE]
> 使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)<br/>
[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[コントロール](../mfc/controls-mfc.md)<br/>