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
ms.openlocfilehash: 45db6d0139cfa3aa8a2eaa8fe6d18158cb6646ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387917"
---
# <a name="resource-files-c"></a>リソース ファイル (C++)

> [!NOTE]
> .NET プログラミング言語のプロジェクトでは、リソース スクリプト ファイルは使用しないため、 **ソリューション エクスプローラー**」をご覧ください。 使用して、[イメージ エディター](../windows/image-editor-for-icons.md)と[バイナリ エディター](binary-editor.md)マネージ プロジェクトのリソース ファイルを使用します。
>
> 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

用語*リソース ファイル*などさまざまな種類のファイルを参照できます。

- プログラムのリソース スクリプト (.rc) ファイル。

- リソース テンプレート (.rct) ファイル。

- 既存のスタンドアロン ファイルとして個々 のリソース。 この型には、ビットマップ、アイコン、またはカーソル、.rc ファイルから参照されるファイルが含まれています。

- 開発環境で生成されたヘッダー ファイル。 この型が含まれています`Resource.h`、.rc ファイルから参照されます。

リソースは、.exe、.dll、.res ファイルと呼びますなどその他のファイルの種類で見つかった*リソース*します。

使用できる*リソース ファイル*と*リソース*から、プロジェクト内で。 現在のプロジェクトの一部ではない、または Visual Studio の開発環境の外部で作成されたもので操作することもできます。 たとえば、次のように操作できます。

- 入れ子になっていて、条件付きでインクルードされるリソース ファイルの操作。

- 既存のリソースを更新し、Visual C に変換したりします。

- グラフィック リソースを現在のリソース ファイルとの間でインポートまたはエクスポートする。

- 開発環境では変更できない共有または読み取り専用識別子 (シンボル) のインクルード。

- 実行可能ファイル (.exe) ファイル編集必要はありません (または編集しないでください)、いくつかのプロジェクト間の共有リソースなどにはのリソースが含まれます。

- 開発環境でサポートされていない種類のリソースのインクルード。

リソースの詳細については、次を参照してください。 方法[リソースの作成](../windows/how-to-create-a-resource-script-file.md)、[リソースの管理](../windows/how-to-copy-resources.md)、および[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。

## <a name="editable-resources"></a>編集可能なリソース

次の種類のファイルが含まれているリソースを編集する開くことができます。

| ファイル名 | 説明 |
|---|---|
| .rc | リソース スクリプト ファイル |
| .rct | リソース テンプレート ファイル |
| .res | リソース ファイル |
| .resx | マネージ リソース ファイル |
| .exe | 実行可能ファイル |
| .dll | ダイナミック リンク ライブラリ ファイル |
| .bmp, .ico, .dib, .cur | ビットマップ、アイコン、ツールバー、およびカーソル ファイル |

リソースを編集するには、Visual Studio 環境は連携して、次のファイルに影響します。

| ファイル名 | 説明 |
|---|---|
| Resource.h | シンボルの定義を含む開発環境で生成されたヘッダー ファイル。<br/><br/>ソース管理には、このファイルを含めます。 |
| Filename.aps | 高速読み込みに使用される現在のリソース スクリプト ファイルのバイナリ バージョンです。<br /><br /> リソース エディターでは、.rc や resource.h ファイルを直接読み取るはありません。 リソース コンパイラは、リソース エディターで使用される .aps ファイルにそれらをコンパイルします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。<br/><br/>通常のコンパイル プロセスでは、コンパイル プロセス中にコメントを記述するなどの記号でない情報が破棄されます。<br/><br/>.Aps ファイルは .rc ファイルが同期されるたびに .rc ファイルを再生成します。 たとえば、する**保存**、リソース エディターは、.rc ファイルと resource.h ファイルが上書きされます。 .Rc ファイルで、リソース自体への変更が組み込まれたままですが、常に、コメントは失われますしたら、.rc ファイルが上書きされます。 コメントを保持する方法については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。<br/><br/>通常、ソース管理に .aps ファイルを含めることはできません。 |
| .rc | 現在のプロジェクト内のリソース用のスクリプトを格納するリソース スクリプト ファイル。 このファイルは、保存するたびに .aps ファイルで上書きされます。<br/><br/>ソース管理には、このファイルを含めます。 |

## <a name="manifest-resources"></a>マニフェスト リソース

C++ デスクトップ プロジェクトでマニフェスト リソースは、アプリケーションを使用して依存関係を記述する XML ファイルです。 たとえば、Visual Studio のこの MFC でウィザードで生成されたマニフェスト ファイルを定義します Windows コモン コントロール Dll のバージョン、アプリケーションを使用する必要があります。

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

Windows XP または Windows Vista アプリケーションでは、マニフェスト リソースはアプリケーションを使用するための Windows コモン コントロールの最新バージョンを指定する必要があります。 上記の例ではバージョン`6.0.0.0`をサポートする、 [Syslink コントロール](/windows/desktop/Controls/syslink-overview)します。

> [!NOTE]
> 使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。

バージョンを表示し、マニフェスト リソースに含まれる情報を入力するには、XML ビューアーや Visual Studio テキスト エディターでファイルを開きます。 マニフェスト リソースを [リソース ビュー](../windows/resource-view-window.md)から開くと、リソースはバイナリ形式で表示されます。

### <a name="to-open-a-manifest-resource"></a>マニフェスト リソースを開く

1. Visual Studio でプロジェクトを開きに移動します**ソリューション エクスプ ローラー**します。

1. 展開、**リソース ファイル**しフォルダー。

   - テキスト エディターで開くをダブルクリックして、 *.manifest*ファイル。

   - 別のエディターで開くを右クリックし、 *.manifest*ファイルおよび選択**ファイルを開く**します。 エディターを使用して、選択を指定**オープン**します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>
[リソース エディター](../windows/resource-editors.md)<br/>