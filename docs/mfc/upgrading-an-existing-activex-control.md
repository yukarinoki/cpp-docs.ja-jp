---
title: 既存の ActiveX コントロールのアップグレード
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX controls [MFC], Internet
- LPK files for Internet controls
- safe for scripting and initialization (controls)
- OLE controls [MFC], upgrading to ActiveX
- CAB files, for ActiveX controls
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], packaging code for download
- upgrading ActiveX controls
- licensing ActiveX controls
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
ms.openlocfilehash: 802640d5132c28dbda564afcb63c12d8a4133042
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353551"
---
# <a name="upgrading-an-existing-activex-control"></a>既存の ActiveX コントロールのアップグレード

既存の ActiveX コントロール (以前の OLE コントロール) は、変更せずにインターネット上で使用できます。 ただし、コントロールのパフォーマンスを向上させるために、コントロールを変更する必要がある場合があります。

> [!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

Web ページでコントロールを使用する場合は、さらに注意点があります。 .ocx ファイルとすべてのサポート ファイルは、ターゲット コンピューター上に置くか、インターネット経由でダウンロードする必要があります。 これにより、コードのサイズとダウンロード時間が重要な考慮事項になります。 ダウンロードは、署名付きの .cab ファイルにパッケージ化できます。 コントロールはスクリプトに対して安全であり、初期化しても安全なコントロールとしてマークできます。

この記事では、次のトピックについて説明します。

- [ダウンロード用のパッケージコード](#_core_packaging_code_for_downloading)

- [スクリプトと初期化に安全なコントロールのマーキング](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [ライセンスに関する問題点](#_core_licensing_issues)

- [署名コード](#_core_signing_code)

- [パレットの管理](#_core_managing_the_palette)

- [インターネット エクスプローラ ブラウザの安全レベルと制御動作](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

[「ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)」の説明に従って、最適化を追加することもできます。 Monikers は、「[インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)」で説明されているように、プロパティや大きな BLOB を非同期的にダウンロードするために使用できます。

## <a name="packaging-code-for-downloading"></a><a name="_core_packaging_code_for_downloading"></a>ダウンロード用のパッケージコード

この問題の詳細については、「 [ActiveX コントロールのパッケージ化](https://docs.microsoft.com//previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29)」を参照してください。

### <a name="the-codebase-tag"></a>コードベースタグ

ActiveX コントロールは、タグを使用して`<OBJECT>`Web ページに埋め込まれます。 タグ`CODEBASE`の`<OBJECT>`パラメーターは、コントロールのダウンロード元の場所を指定します。 `CODEBASE`さまざまなファイルの種類を正常に指定できます。

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>OCX ファイルでの CODEBASE タグの使用

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

このソリューションでは、コントロールの .ocx ファイルのみがダウンロードされ、サポートする DLL がクライアント コンピュータに既にインストールされている必要があります。 この方法は、Visual C++ で作成されたインターネット エクスプローラおよび MFC ActiveX コントロールに対しては機能します。 ActiveX コントロールに対応した別のインターネット ブラウザを使用してこのコントロールを表示した場合、このソリューションは機能しません。

### <a name="using-the-codebase-tag-with-an-inf-file"></a>INF ファイルでのコードベース タグの使用

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

.inf ファイルは、.ocx とそのサポート ファイルのインストールを制御します。 .inf ファイルに署名することはできないため、この方法はお勧めしません (コード署名のポインタについては[、「コードの署名](#_core_signing_code)」を参照してください)。

### <a name="using-the-codebase-tag-with-a-cab-file"></a>CAB ファイルでのコードベース タグの使用

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

MFC を使用する ActiveX コントロールをパッケージ化する場合は、キャビネット ファイルを使用することをお勧めします。 MFC ActiveX コントロールをキャビネット ファイルにパッケージ化すると、.inf ファイルを含め、ActiveX コントロールと依存 DLL (MFC DLL など) のインストールを制御できます。 CAB ファイルを使用すると、コードが自動的に圧縮され、ダウンロードが速く行われます。 コンポーネントのダウンロードに .cab ファイルを使用している場合は、各コンポーネントよりも .cab ファイル全体に署名する方が高速です。

### <a name="creating-cab-files"></a>CAB ファイルの作成

キャビネット ファイルを作成するツールは[、Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)の一部になりました。

に示す`CODEBASE`キャビネット ファイルには、ActiveX コントロール用の .ocx ファイルと、インストールを制御する .inf ファイルが含まれている必要があります。 キャビネット ファイルを作成するには、コントロール ファイルの名前と .inf ファイルを指定します。 このキャビネット ファイルに、システム上に既に存在する依存 DLL は含めないでください。 たとえば、MFC DLL は別のキャビネット ファイルにパッケージ化され、制御する .inf ファイルによって参照されます。

CAB ファイルの作成方法の詳細については[、CAB ファイルの作成を](/windows/win32/devnotes/cabinet-api-functions)参照してください。

### <a name="the-inf-file"></a>INF ファイル

次の例 spindial.inf は、MFC スピンダイヤル コントロールに必要なサポート ファイルとバージョン情報を一覧表示します。 MFC DLL の場所はマイクロソフトの Web サイトであることに注意してください。 mfc42.cab はマイクロソフトによって提供され、署名されています。

```
Contents of spindial.inf:
[mfc42installer]
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab
[Olepro32.dll] - FileVersion=5,
    0,
    4261,
    0
[Mfc42.dll] - FileVersion=6,
    0,
    8168,
    0
[Msvcrt.dll] - FileVersion=6,
    0,
    8168,
    0
```

### <a name="the-object-tag"></a>\<オブジェクト> タグ

次の例は、MFC`<OBJECT>`スピンディアル サンプル コントロールをパッケージ化するタグを使用する方法を示しています。

```
<OBJECT ID="Spindial1" WIDTH=100 HEIGHT=51
    CLASSID="CLSID:06889605-B8D0-101A-91F1-00608CEAD5B3"
    CODEBASE="http://example.microsoft.com/spindial.cab#Version=1,0,0,001">
<PARAM NAME="_Version" VALUE="65536">
<PARAM NAME="_ExtentX" VALUE="2646">
<PARAM NAME="_ExtentY" VALUE="1323">
<PARAM NAME="_StockProps" VALUE="0">
<PARAM NAME="NeedlePosition" VALUE="2">
</OBJECT>
```

この場合、spindial.cab には spindial.ocx と spindial.inf という 2 つのファイルが含まれます。 次のコマンドを実行すると、キャビネット ファイルが作成されます。

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

パラメーター`-s 6144`は、コード署名用にキャビネット内の領域を確保します。

### <a name="the-version-tag"></a>バージョン タグ

ここでは、CAB`#Version`ファイルで指定された情報は、タグの*CLASSID*パラメーターで指定されたコントロール`<OBJECT>`に適用されることに注意してください。

指定したバージョンに応じて、コントロールを強制的にダウンロードできます。 *CODEBASE*パラメーターを`OBJECT`含むタグの完全な仕様については、W3C リファレンスを参照してください。

## <a name="marking-a-control-safe-for-scripting-and-initializing"></a><a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a>スクリプトと初期化に安全なコントロールのマーキング

Web ページで使用されている ActiveX コントロールは、スクリプトを実行しても安全であり、実際には安全な場合は初期化しても安全であるとマークする必要があります。 安全なコントロールはディスク IO を実行したり、コンピュータのメモリやレジスタに直接アクセスしたりしません。

コントロールは、スクリプトを実行しても安全であり、レジストリを使用して初期化しても安全であるとマークできます。 次`DllRegisterServer`のようなエントリを追加して、レジストリ内のスクリプトと永続化に対して安全なコントロールとしてマークするように変更します。 別の方法として、`IObjectSafety`を実装する方法があります。

コントロールの GUID (グローバル一意識別子) を定義して、スクリプトと永続化に対して安全なマークを付けます。 安全にスクリプトを作成できるコントロールには、次のようなレジストリ エントリが含まれます。

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

永続データから安全に初期化できるコントロールは、次のようなレジストリ エントリを使用して、永続化のために安全であるとマークされます。

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

キーを次のクラス ID に関連付けるには、次のようなエントリを追加します`{06889605-B8D0-101A-91F1-00608CEAD5B3}`( コントロールのクラス ID を代わりに ) します。

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

## <a name="licensing-issues"></a><a name="_core_licensing_issues"></a>ライセンスに関する問題

Web ページでライセンスコントロールを使用する場合は、使用許諾契約書がインターネットで使用できるかどうかを確認し、そのライセンス パッケージ ファイル (LPK) を作成する必要があります。

Internet Explorer を実行しているコンピュータがコントロールを使用するライセンスを持っていない場合、ライセンスを取得した ActiveX コントロールは HTML ページに正しく読み込まれません。 たとえば、Visual C++ を使用してコントロールを作成した場合、コントロールを使用する HTML ページは、コントロールが作成されたコンピュータに正しく読み込まれますが、ライセンス情報が含まれていない限り、別のコンピュータに読み込まれません。

ライセンスを取得した ActiveX コントロールを Internet Explorer で使用するには、ベンダーのライセンス契約を確認して、コントロールのライセンスが許可されていることを確認する必要があります。

- 再配布

- インターネット上でのコントロールの使用

- コードベース パラメーターの使用

ライセンスを持たないマシンの HTML ページでライセンスコントロールを使用するには、ライセンス パッケージ ファイル (LPK) を生成する必要があります。 LPK ファイルには、HTML ページ内のライセンスコントロールのランタイム ライセンスが含まれています。 このファイルは、LPK_TOOLを介して生成されます。EXE は、ActiveX SDK に付属しています。

#### <a name="to-create-an-lpk-file"></a>LPK ファイルを作成するには

1. LPK_TOOLを実行します。EXE は、コントロールを使用するライセンスが付与されているコンピュータ上で実行されます。

1. [**ライセンス パッケージ オーサリング ツール**] ダイアログ ボックスの [**使用可能なコントロール**] リスト ボックスで、HTML ページで使用するライセンスを持つ ActiveX コントロールを選択し、[**追加**] をクリックします。

1. [**保存& Exit]** をクリックし、LPK ファイルの名前を入力します。 LPK ファイルが作成され、アプリケーションが閉じます。

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>HTML ページにライセンスコントロールを埋め込むには

1. HTML ページを編集します。 HTML ページで、他\<\<の OBJECT> タグの前に、ライセンス マネージャー オブジェクトの OBJECT> タグを挿入します。 ライセンス マネージャは、インターネット エクスプローラと共にインストールされる ActiveX コントロールです。 そのクラス ID は以下に示されています。 ライセンス マネージャ オブジェクトの LPKPath プロパティを LPK ファイルのパスと名前に設定します。 1 つの HTML ページに 1 つの LPK ファイルしか持てなされない。

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. ライセンス\<マネージャー タグの後に、ライセンス コントロールの OBJECT> タグを挿入します。

   たとえば、Microsoft マスク エディット コントロールを表示する HTML ページを次に示します。 最初のクラス ID はライセンス マネージャー コントロール用で、2 番目のクラス ID はマスク エディット コントロール用です。 前に作成した .lpk ファイルの相対パスを指すタグを変更し、コントロールのクラス ID を含むオブジェクト タグを追加します。

1. NCompass ActiveX プラグインを\<使用している場合は、LPK ファイルの EMBED>属性を挿入します。

   コントロールが他のアクティブな有効なブラウザ (たとえば、NCompass ActiveX プラグインを使用した Netscape) で表示される\<場合は、以下に示すように EMBED>構文を追加する必要があります。

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

コントロール ライセンスの詳細については、「 [ActiveX コントロール : ActiveX コントロールのライセンスを取得する](../mfc/mfc-activex-controls-licensing-an-activex-control.md)」を参照してください。

## <a name="signing-code"></a><a name="_core_signing_code"></a>署名コード

コード署名は、コードのソースを識別し、署名後にコードが変更されないことを保証するように設計されています。 ブラウザの安全性の設定によっては、コードがダウンロードされる前に警告が表示されることがあります。 ユーザーは、特定の証明書所有者または企業を信頼することを選択することができ、その場合、信頼された証明書によって署名されたコードは警告なしにダウンロードされます。 コードは改ざんを防ぐためにデジタル署名されています。

信頼の警告メッセージを表示せずにコントロールを自動的にダウンロードできるように、最終的なコードが署名されていることを確認します。 コードに署名する方法の詳細については、ActiveX SDK の Authenticode のドキュメントを参照し[、CAB ファイルの署名を](/windows/win32/devnotes/cabinet-api-functions)参照してください。

信頼とブラウザーの安全性レベルの設定によっては、署名者または会社を識別する証明書が表示される場合があります。 安全レベルが none の場合、または署名されたコントロールの証明書の所有者が信頼されている場合は、証明書は表示されません。 コントロールがダウンロードされ、証明書が表示されるかどうかをブラウザーの安全性設定によって決定する方法の詳細については[、「Internet Explorer ブラウザの安全性レベルとコントロールの動作](#_core_internet_explorer_browser_safety_levels_and_control_behavior)」を参照してください。

デジタル署名は、署名されたコードが変更されていないことを保証します。 コードのハッシュが取得され、証明書に埋め込まれます。 このハッシュは、コードのダウンロード後、実行前に取得されたコードのハッシュと後で比較されます。 ベリサインなどの企業は、コードに署名するために必要な秘密鍵と公開鍵を提供できます。 ActiveX SDK には、テスト証明書を作成するためのユーティリティである MakeCert が付属しています。

## <a name="managing-the-palette"></a><a name="_core_managing_the_palette"></a>パレットの管理

コンテナはパレットを決定し、アンビエント プロパティとして使用できるようにします **(DISPID_AMBIENT_PALETTE。** コンテナ (Internet Explorer など) は、ページ上のすべての ActiveX コントロールが使用するパレットを選択して、独自のパレットを決定します。 これにより、表示がちらつき防止され、一貫した外観が表示されます。

コントロールは、パレット`OnAmbientPropertyChange`への変更の通知を処理するためにオーバーライドできます。

コントロールは、パレット`OnGetColorSet`を描画するカラー セットを返すようにオーバーライドできます。 コンテナーは、戻り値を使用して、コントロールがパレット対応かどうかを判断します。

OCX 96 ガイドラインでは、コントロールは常にバックグラウンドでパレットを認識する必要があります。

アンビエント パレット プロパティを使用しない古いコンテナは、WM_QUERYNEWPALETTEおよびWM_PALETTECHANGEDメッセージを送信します。 コントロールは、これらの`OnQueryNewPalette`メッセージ`OnPaletteChanged`をオーバーライドして処理できます。

## <a name="internet-explorer-browser-safety-levels-and-control-behavior"></a><a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a>インターネット エクスプローラ ブラウザの安全レベルと制御動作

ブラウザには、ユーザが設定可能な安全レベルのオプションがあります。 Web ページにはユーザーのコンピュータに悪影響を及ぼす可能性のあるアクティブ コンテンツが含まれる可能性があるため、ブラウザではユーザーが安全レベルのオプションを選択できます。 ブラウザーが安全レベルを実装する方法によっては、コントロールがダウンロードされない場合や、ユーザーがコントロールをダウンロードするかどうかを実行時に選択できるように証明書または警告メッセージが表示される場合があります。 以下に、Internet Explorer の高、中、および低レベルのレベルでの ActiveX コントロールの動作を示します。

### <a name="high-safety-mode"></a>高い安全モード

- 署名されていないコントロールはダウンロードされません。

- 署名されたコントロールは、信頼されていない場合に証明書を表示します (ユーザーは、この証明書所有者からのコードを常に信頼するオプションを選択できます)。

- 安全とマークされたコントロールのみが、永続的なデータを持つ、またはスクリプト可能になります。

### <a name="medium-safety-mode"></a>中安全モード

- 署名されていないコントロールは、ダウンロードの前に警告を表示します。

- 署名されたコントロールは、信頼されていない場合は証明書を表示します。

- 安全としてマークされていないコントロールには警告が表示されます。

### <a name="low-safety-mode"></a>低い安全モード

- コントロールは警告なしにダウンロードされます。

- スクリプトと永続性は警告なしに行われます。

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC ActiveX コントロール : ActiveX コントロールのライセンス](../mfc/mfc-activex-controls-licensing-an-activex-control.md)
