---
title: リソース ファイル (C++)
ms.date: 02/14/2019
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
ms.openlocfilehash: 4d56a62dfa350b3113a28355433130563464c6be
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320537"
---
# <a name="resource-files-c"></a>リソース ファイル (C++)

> [!NOTE]
> .NET プログラミング言語のプロジェクトでは、リソース スクリプト ファイルは使用しないため、 **ソリューション エクスプローラー**」をご覧ください。 [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージド プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

"リソース ファイル" という用語は、次のようなさまざまな種類のファイルを示します。

- プログラムのリソース スクリプト (.rc) ファイル。

- リソース テンプレート (.rct) ファイル。

- ビットマップ、アイコン、カーソル ファイルなど、スタンドアロン ファイルとして存在し、.rc ファイルから参照される個別のリソース。

- Resource.h など、開発環境で生成され、.rc ファイルから参照されるヘッダー ファイル。

リソースは、.exe、.dll、.res ファイルなどの他のファイルの種類にも存在します。 現在のプロジェクトの一部ではないものと、プロジェクト内でリソースとリソース ファイルを使用できます。 Visual Studio の開発環境で作成されていないリソース ファイルを操作することもできます。 たとえば、次のように操作できます。

- 入れ子になっていて、条件付きでインクルードされるリソース ファイルの操作。

- 既存のリソースの更新、または Visual C++ 形式への変換。

- グラフィック リソースを現在のリソース ファイルとの間でインポートまたはエクスポートする。

- 開発環境では変更できない共有または読み取り専用識別子 (シンボル) のインクルード。

- 実行可能ファイル (.exe) ファイルの編集を必要としない (または編集することはできません) 中にいくつかのプロジェクト間の共有リソースなど、現在のプロジェクトにリソースが含まれます。

- 開発環境でサポートされていない種類のリソースのインクルード。

このセクションでは方法。

- [リソースを作成します。](../windows/how-to-create-a-resource-script-file.md)

- [リソースを管理します。](../windows/how-to-copy-resources.md)

- [コンパイル時にリソースを含める](../windows/how-to-include-resources-at-compile-time.md)

## <a name="editable-resource-file-types"></a>編集可能なリソース ファイルの種類

次の種類のファイルが含まれているリソースを編集する開くことができます。

|ファイル名|説明|
|---------|-----------------|
|.rc|リソース スクリプト ファイル|
|.rct|リソース テンプレート ファイル|
|.res|リソース ファイル|
|.resx|マネージ リソース ファイル|
|.exe|実行可能ファイル|
|.dll|ダイナミック リンク ライブラリ ファイル|
|.bmp、.ico、.dib、.cur|ビットマップ、アイコン、ツール バー、カーソルのファイル。|

Visual Studio 環境では、連携して、リソース編集セッション中に、次のファイルに影響を与えます。

|ファイル名|説明|
|---------------|-----------------|
|Resource.h|開発環境で生成されるヘッダー ファイル。シンボル定義が含まれます。 (このファイルはソース管理に含めます。)|
|Filename.aps|高速読み込みに使用される、現在のリソース スクリプト ファイルのバイナリ バージョン。<br /><br /> リソース エディターでは、.rc や resource.h ファイルを直接読み取るはありません。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスでは、コンパイル プロセス中にシンボリック (たとえば、コメントなど) でない情報が破棄されます。 .aps ファイルと .rc ファイルが同期しなくなると、そのたびに .rc ファイルが再生成されます (たとえば、[保存] を実行すると、リソース エディターによって .rc ファイルと resource.h ファイルが上書きされます)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。 コメントを保持する方法については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。 (通常は、するべきではない .aps ファイルに含めるソース管理。)|
|.rc|現在のプロジェクト内のリソース用のスクリプトを格納するリソース スクリプト ファイル。 このファイルは、保存するたびに .aps ファイルで上書きされます。 (このファイルはソース管理に含めます。)|

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

### <a name="to-open-a-manifest-resource"></a>マニフェスト リソースを開く

1. Visual Studio でプロジェクトを開きます。

1. 移動します**ソリューション エクスプ ローラー**を展開し、**リソース ファイル**フォルダー。

   - テキスト エディターの .manifest ファイルをダブルクリックします。

   - 、他のエディターの .manifest ファイルを右クリックし、選択**プログラムから開く.**、エディターを使用して、選択を指定し、**オープン**します。

> [!NOTE]
> 使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>
[リソース エディター](../windows/resource-editors.md)<br/>