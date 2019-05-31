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
ms.openlocfilehash: 57d94a51d9dfb78dfaf3a690c43c74a2d6ab6db3
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450602"
---
# <a name="upgrading-an-existing-activex-control"></a>既存の ActiveX コントロールのアップグレード

既存の ActiveX コントロール (以前の OLE コントロール) 変更しなくても、インターネットで使用できます。 ただし、それぞれのパフォーマンスを向上させるためにコントロールを変更することがあります。

> [!IMPORTANT]
> ActiveX は、新規の開発が使用できないレガシ テクノロジです。 ActiveX の置き換えの最新のテクノロジの詳細については、次を参照してください。 [ActiveX コントロール](activex-controls.md)します。

Web ページ上にコントロールを使用する場合は、追加の考慮事項です。 .Ocx ファイルとすべてのサポート ファイルは、ターゲット コンピューターである必要がありますか、インターネット経由でダウンロードします。 これにより、コードのサイズと時間の重要な考慮事項をダウンロードします。 ダウンロードは、署名された .cab ファイルにパッケージ化することができます。 コントロール、スクリプトの安全性および初期化に対して安全としてマークできます。

この記事では、次のトピックについて説明します。

- [ダウンロード用のコードをパッケージ化](#_core_packaging_code_for_downloading)

- [スクリプトと初期化の安全性をマークします。](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [ライセンスの問題](#_core_licensing_issues)

- [コードの署名](#_core_signing_code)

- [パレットの管理](#_core_managing_the_palette)

- [Internet Explorer ブラウザーの安全性レベルとコントロールの動作](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

最適化を追加することも[ActiveX コントロール。最適化](../mfc/mfc-activex-controls-optimization.md)します。 プロパティをダウンロードするモニカーを使用でき、サイズの大きな Blob を非同期的に、」の説明に従って[インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)します。

##  <a name="_core_packaging_code_for_downloading"></a> ダウンロード用のコードをパッケージ化

このトピックの詳細については、次を参照してください。 [ActiveX コントロールをパッケージ化](https://docs.microsoft.com//previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29)します。

### <a name="the-codebase-tag"></a>コードベースのタグ

ActiveX コントロールを使用して Web ページに埋め込まれている、`<OBJECT>`タグ。 `CODEBASE`のパラメーター、`<OBJECT>`タグは、コントロールのダウンロード元の場所を指定します。 `CODEBASE` ポイント数の異なる種類のファイルが正常にされます。

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>OCX ファイルを使用して、コードベースのタグを使用します。

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

このソリューションでは、コントロールの .ocx ファイルのみをダウンロードし、既にクライアント コンピューターにインストールするサポートの Dll が必要です。 これには、Internet Explorer が Visual C のコントロール用の Dll はサポートが付属していますので、Visual C でビルドされた Internet Explorer および MFC ActiveX コントロールの機能はします。 このコントロールを表示するのには ActiveX コントロールに対応する別のインターネット ブラウザーを使用する場合、このソリューションは機能しません。

### <a name="using-the-codebase-tag-with-an-inf-file"></a>INF ファイルを使用して、コードベースのタグを使用します。

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

.Inf ファイルは、.ocx およびそのサポート ファイルのインストールを制御します。 .Inf ファイルに署名することはできませんので、この方法は推奨されません (を参照してください[コードの署名](#_core_signing_code)のコード署名のポインター)。

### <a name="using-the-codebase-tag-with-a-cab-file"></a>CAB ファイルを使用して、コードベースのタグを使用します。

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

キャビネット ファイルは、MFC を使用する ActiveX コントロールをパッケージに推奨される方法です。 ActiveX コントロールおよびすべての依存 Dll (MFC Dll) などのコントロールのインストールに含まれる、.inf ファイルをキャビネット ファイルに MFC ActiveX コントロールをパッケージ化できます。 CAB ファイルを自動的に使用するには、ダウンロード時間を短縮するためのコードで圧縮されます。 コンポーネントのダウンロードを .cab ファイルを使用している場合もすばやく個々 のコンポーネントよりも全体の .cab ファイルに署名します。

### <a name="creating-cab-files"></a>CAB ファイルを作成します。

キャビネット ファイルを作成するツールは、の一部となって、 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)します。

キャビネット ファイルが指す`CODEBASE`ActiveX コントロールの .ocx ファイルとそのインストールを制御する .inf ファイルに含める必要があります。 キャビネット ファイル、コントロールのファイルの名前を指定することで、.inf ファイルを作成します。 既にこのキャビネット ファイルで、システムに存在する依存 Dll を含めないでください。 たとえば、MFC Dll が別のキャビネット ファイルにパッケージ化され、制御の .inf ファイルで参照します。

CAB ファイルを作成する方法の詳細については、次を参照してください。 [CAB ファイルを作成する](/windows/desktop/devnotes/cabinet-api-functions)します。

### <a name="the-inf-file"></a>INF ファイル

次の例、spindial.inf、リスト サポート ファイルとバージョンについては、必要な MFC Spindial を制御します。 MFC Dll の場所は、Microsoft Web サイトに注意してください。 Mfc42.cab が提供され、Microsoft によって署名されました。

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

### <a name="the-object-tag"></a>\<オブジェクト > タグ

次の例を使用して、 `<OBJECT>` MFC Spindial サンプル コントロールをパッケージ化するタグ。

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

この場合、2 つのファイルや spindial.ocx spindial.inf spindial.cab が含まれます。 次のコマンドはキャビネット ファイルを作成します。

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

`-s 6144`パラメーターは、コード署名用キャビネットの領域を確保します。

### <a name="the-version-tag"></a>バージョンのタグ

ここで注意、 `#Version` CAB ファイルで指定した情報で指定されたコントロールに適用されます、 *CLASSID*のパラメーター、`<OBJECT>`タグ。

指定したバージョンに応じて、コントロールのダウンロードを強制できます。 完全な仕様については、`OBJECT`タグを含む、*コードベース*パラメーター、リファレンス、W3C を参照してください。

##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> スクリプトと初期化の安全性をマークします。

Web ページで使用されている ActiveX コントロールは、スクリプトを実行してとを初期化する場合、それらが安全では実際の安全性としてマークする必要があります。 安全なコントロールは、ディスク IO を実行またはメモリやマシンのレジスタに直接アクセスはできません。

コントロールは、スクリプトにとって安全だとレジストリを使用して初期化するため安全としてマークすることができます。 変更`DllRegisterServer`としてスクリプトとレジストリに永続化の安全なコントロールをマークするには、次のようなエントリを追加します。 別の方法は、実装する`IObjectSafety`します。

スクリプトを実行して、永続化の安全をマークするコントロールの Guid (グローバルに一意の識別子) を定義します。 安全にスクリプトを作成できるコントロールは、次のようなレジストリ エントリが含まれます。

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

永続的なデータから安全に初期化できるコントロールを安全に使用して永続化のようなレジストリ エントリがマークされます。

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

次のようなエントリを追加 (クラスの代わりに ID を置き換えて、コントロールの`{06889605-B8D0-101A-91F1-00608CEAD5B3}`) に次のクラス ID、キーを関連付けます。

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

##  <a name="_core_licensing_issues"></a> ライセンスの問題

Web ページでライセンスされたコントロールを使用するには、使用許諾契約書は、インターネット上の使用が使用し、そのライセンス パッケージ ファイル (LPK) を作成を確認する必要があります。

ライセンスされた ActiveX コントロールは読み込まれません正しく HTML ページにコントロールを使用して Internet Explorer を実行しているコンピューターがライセンス許諾されていない場合。 たとえば、ライセンスされたコントロールは、Visual C を使用して構築された場合、コントロールを使用する HTML ページは正常に読み込まコンピューターでコントロールが作成されたが、ライセンス情報が含まれていない限り、別のコンピューターでは読み込まれません。

Internet Explorer でライセンスされた ActiveX コントロールを使用するには、コントロールのライセンスができることを確認するベンダーの使用許諾契約書を確認する必要があります。

- 再配布

- インターネット上のコントロールの使用

- コードベースのパラメーターの使用

ライセンスのないコンピューターで、HTML ページでライセンスされたコントロールを使用するには、ライセンス パッケージ ファイル (LPK) を生成する必要があります。 LPK ファイルには、HTML ページでライセンスされたコントロールの実行時のライセンスが含まれています。 このファイルは、LPK_TOOL を使用して生成されます。ActiveX SDK に付属している実行可能ファイルです。 詳細については、MSDN Web サイトを参照してください。 [ https://msdn.microsoft.com](https://msdn.microsoft.com)します。

#### <a name="to-create-an-lpk-file"></a>LPK ファイルを作成するには

1. LPK_TOOL を実行します。コントロールの使用がライセンスされているコンピューター上の exe ファイル。

1. **ライセンス パッケージ Authoring Tool**  ダイアログ ボックスで、**利用可能なコントロール**リスト ボックスで、それぞれ選択がライセンスされた ActiveX コントロール、HTML ページで使用され、をクリックする**追加**.

1. をクリックして**保存して終了.** LPK ファイルの名前を入力します。 LPK ファイルが作成され、アプリケーションを閉じます。

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>HTML ページでライセンスされたコントロールを埋め込むには

1. HTML ページを編集します。 HTML ページで、挿入、\<オブジェクト > タグの前に、他のライセンス マネージャー オブジェクト\<オブジェクト > タグです。 ライセンス マネージャーは、Internet Explorer と共にインストールされる ActiveX コントロールです。 そのクラスの ID は、以下に示します。 LPK ファイルの名前とパスを LPKPath ライセンス マネージャー オブジェクトのプロパティを設定します。 HTML ページごとに 1 つだけ LPK ファイルがあることができます。

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. 挿入、\<オブジェクト > License Manager タグの後にライセンスされたコントロールのタグ。

   たとえば、Microsoft のマスク エディット コントロールを表示する HTML ページは、以下に示します。 ID は、License Manager コントロールの最初のクラス、マスク エディット コントロールの ID は、2 番目のクラス。 前に作成した .lpk ファイルの相対パスを指すタグを変更し、コントロールのクラス ID を含むオブジェクト タグを追加します。

1. 挿入、\<埋め込み > NCompass ActiveX プラグインを使用する場合、LPK ファイルの属性します。

   アクティブによってブラウザーが有効になっている場合、他のコントロールを表示することがあります: NCompass ActiveX プラグインを使用して Netscape など、追加する必要があります、\<埋め込み > 構文を次に示すよう。

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

コントロールのライセンスの詳細については、次を参照してください。 [ActiveX コントロール。ActiveX コントロールのライセンス](../mfc/mfc-activex-controls-licensing-an-activex-control.md)します。

##  <a name="_core_signing_code"></a> コードの署名

コード署名は、コードのソースを識別するために設計されていて、署名されたので、コードが変更されていないことを保証するためにします。 ブラウザーの安全性設定によって、コードをダウンロードする前に、ユーザーを警告可能性があります。 ユーザーは、特定の証明書の所有者またはそれらによって署名された大文字と小文字のコードが警告なしにダウンロードが信頼された企業を信頼する選択できます。 コードは、改ざんを回避するためにデジタル署名します。

信頼の警告メッセージを表示せず、コントロールを自動的にダウンロードできるように、最終的なコードが署名を確認します。 コードに署名する方法の詳細については、Authenticode ActiveX sdk に関するドキュメントを確認しを参照してください[CAB ファイルへの署名](/windows/desktop/devnotes/cabinet-api-functions)します。

信頼とブラウザーの安全性レベル設定によって、証明書が署名した個人または会社を識別するために表示されます。 安全性レベルが none、署名されたコントロールの証明書の所有者が信頼されている場合や、証明書は表示されません。 参照してください[Internet Explorer ブラウザーの安全性レベルと動作を制御](#_core_internet_explorer_browser_safety_levels_and_control_behavior)コントロールをダウンロードするかどうかと証明書の表示のブラウザーの安全性設定の特定方法の詳細について。

署名されているために、デジタル署名の保証のコードは変更されていません。 コードのハッシュが取得され、証明書に埋め込まれています。 このハッシュ コードをダウンロードした後は、実行前に実行されるコードのハッシュと比較します。 Verisign などの企業では、コードの署名に必要なプライベートおよびパブリックのキーを指定できます。 ActiveX SDK は、MakeCert、テスト証明書を作成するためのユーティリティでは出荷されます。

##  <a name="_core_managing_the_palette"></a> パレットの管理

コンテナーがパレットを決定し、アンビエント プロパティとして使用できるように**DISPID_AMBIENT_PALETTE**します。 コンテナー (たとえば、Internet Explorer) は、ページ上のすべての ActiveX コントロールで、独自のパレットを決定するために使用するパレットを選択します。 これは、は、ディスプレイのちらつきをできなくなり、一貫性のある外観を表示します。

オーバーライドする`OnAmbientPropertyChange`パレットを変更の通知を処理します。

オーバーライドする`OnGetColorSet`をパレットを描画するために設定する色を返します。 コンテナーは、コントロールがパレットに対応したかを判断するのに戻り値を使用します。

OCX 96 ガイドラインでは、コントロールは、バック グラウンドでは、そのパレットを常に認識する必要があります。

パレットのアンビエント プロパティを使用しない古いコンテナーでは、WM_QUERYNEWPALETTE とするとメッセージを送信します。 オーバーライドする`OnQueryNewPalette`と`OnPaletteChanged`これらのメッセージを処理します。

##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Internet Explorer ブラウザーの安全性レベルとコントロールの動作

ブラウザーでは、安全性レベルは、ユーザーが構成可能なオプションがあります。 Web ページには、ユーザーのコンピューターに損害を与える可能性がある可能性がありますのアクティブ コンテンツを含めることができます、ため、ブラウザーは、ユーザーの安全性レベルのオプションを選択を許可します。 によって、ブラウザーが安全性レベルを実装する方法、コントロールは、ダウンロードできません可能性があります。 または証明書またはユーザーが実行時にコントロールをダウンロードするかどうか選択を許可する警告メッセージが表示されます。 Internet Explorer で、高、中、低の安全性レベルでの ActiveX コントロールの動作は、以下に記載されています。

### <a name="high-safety-mode"></a>高い安全性モード

- 符号なしのコントロールはダウンロードされません。

- 署名されたコントロールは、信頼されていない場合、証明書に表示されます (ユーザーは、常にこの証明書の所有者からコードを信頼するためのオプションを選択できます)。

- 安全としてマークされているコントロールだけは永続的なデータや、スクリプトを実行します。

### <a name="medium-safety-mode"></a>中規模の安全性モード

- 署名されていないコントロールをダウンロードする前に警告が表示されます。

- 信頼されていない場合、署名されたコントロールは、証明書に表示されます。

- 安全としてマークされていないコントロール警告が表示されます。

### <a name="low-safety-mode"></a>安全性-低のモード

- コントロールは、警告なしにダウンロードされます。

- スクリプトの作成と永続化警告なしに発生します。

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC ActiveX コントロール: ActiveX コントロールのライセンス](../mfc/mfc-activex-controls-licensing-an-activex-control.md)
