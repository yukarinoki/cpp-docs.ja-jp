---
title: 既存の ActiveX コントロールのアップグレード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e40240367d3e8350cee030b2c08dc5a48325e05f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="upgrading-an-existing-activex-control"></a>既存の ActiveX コントロールのアップグレード
既存の ActiveX コントロール (以前の OLE コントロール) 変更しなくても、インターネットで使用できます。 ただし、これらのパフォーマンスを向上させるためにコントロールを変更する可能性があります。 Web ページ上のコントロールを使用するときは、追加の考慮事項があります。 .Ocx ファイルとすべてのサポート ファイルは、対象のコンピューターである必要がありますか、インターネット経由でダウンロードします。 これにより、コードのサイズとダウンロードにかかる時間の重要な注意します。 ダウンロードは、署名済み .cab ファイルにパッケージ化することができます。 安全なスクリプト、および初期化の安全性として、コントロールをマークすることができます。  
  
 この記事では、次のトピックについて説明します。  
  
- [パッケージのコードをダウンロードします。](#_core_packaging_code_for_downloading)  
  
- [スクリプトと初期化の安全性をマークします。](#_core_marking_a_control_safe_for_scripting_and_initializing)  
  
- [ライセンスの問題](#_core_licensing_issues)  
  
- [コードの署名](#_core_signing_code)  
  
- [パレットの管理](#_core_managing_the_palette)  
  
- [Internet Explorer ブラウザーの安全性レベルとコントロールの動作](#_core_internet_explorer_browser_safety_levels_and_control_behavior)  
  
 最適化を追加することも[ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)です。 プロパティのダウンロードにモニカーを使用することができ、大きな Blob を非同期で説明されている[、インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)です。  
  
##  <a name="_core_packaging_code_for_downloading"></a> パッケージのコードをダウンロードします。  
 このトピックの詳細については、サポート技術情報の記事「パッケージング MFC コントロールを使用して経由でインターネット」(Q167158) を参照してください。 サポート技術情報を見つけることができます[ http://support.microsoft.com/support](http://support.microsoft.com/support)です。  
  
### <a name="the-codebase-tag"></a>CODEBASE タグ  
 ActiveX コントロールが使用する Web ページに埋め込まれている、`<OBJECT>`タグ。 `CODEBASE`のパラメーター、`<OBJECT>`タグは、コントロールをダウンロードする元の場所を指定します。 `CODEBASE` ポイントで異なる種類のファイルの数が正常にされます。  
  
### <a name="using-the-codebase-tag-with-an-ocx-file"></a>OCX ファイルを使用して、CODEBASE タグを使用します。  
  
```  
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"  
```  
  
 このソリューションでは、コントロールの .ocx ファイルのみをダウンロードし、既にインストールされているクライアント コンピューターをサポートする Dll が必要です。 これには、Internet Explorer が Visual C のコントロールのサポートの Dll が付属していますので、Visual C でビルドされた Internet Explorer と MFC ActiveX コントロールの機能はします。 別のインターネット ブラウザーでは、ActiveX コントロール対応を介してこのコントロールを表示する場合に、このソリューションは機能しません。  
  
### <a name="using-the-codebase-tag-with-an-inf-file"></a>INF ファイルを使用して、CODEBASE タグを使用します。  
  
```  
CODEBASE="http://example.microsoft.com/trustme.inf"  
```  
  
 .Inf ファイルは、.ocx、およびそのサポート ファイルのインストールを制御します。 このメソッドは .inf ファイルに署名することはできませんので使用しないで (を参照してください[コードの署名](#_core_signing_code)コード署名のポインターの)。  
  
### <a name="using-the-codebase-tag-with-a-cab-file"></a>CAB ファイルを使用して、CODEBASE タグを使用します。  
  
```  
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"  
```  
  
 キャビネット ファイルは、MFC を使用するパッケージの ActiveX コントロールに推奨される方法です。 ActiveX コントロールとその依存 Dll (MFC Dll) などのコントロールのインストールに含まれるように、.inf ファイルをキャビネット ファイルに MFC ActiveX コントロールをパッケージ化できます。 CAB ファイルから自動的に使用すると、すばやくダウンロード用のコードが圧縮されます。 コンポーネントのダウンロードを .cab ファイルを使用している場合をすばやく個々 のコンポーネントよりも全体の .cab ファイルに署名します。  
  
### <a name="creating-cab-files"></a>CAB ファイルを作成します。  
 キャビネット開発キットをダウンロードするには、サポート技術情報の記事から[310618: Microsoft キャビネット Software Development Kit](http://go.microsoft.com/fwlink/p/?linkid=148204)です。 このキットには、キャビネット ファイルを構築するために必要なツールを紹介します。  
  
 キャビネット ファイルを指す`CODEBASE`ActiveX コントロールの .ocx ファイルとそのインストールを制御する .inf ファイルが含まれています。 キャビネット ファイル、コントロールのファイルの名前を指定することによって、.inf ファイルを作成します。 システム上でこのキャビネット ファイルが既に存在する依存 Dll を含めないでください。 たとえば、MFC Dll が別のキャビネット ファイルにパッケージ化し、制御の .inf ファイルで参照します。  
  
 CAB ファイルを作成する方法の詳細については、「 [CAB ファイルを作成する](http://msdn.microsoft.com/en-us/cc52fd09-bdf6-4410-a693-149a308f36a3)です。  
  
### <a name="the-inf-file"></a>INF ファイル  
 次の例、spindial.inf、リストのサポート ファイルとバージョンについては、必要な MFC Spindial を制御します。 MFC Dll の場所は、Microsoft Web サイトに注意してください。 Mfc42.cab が提供され、Microsoft によって署名します。  
  
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
 次の例を使用して、 `<OBJECT>` MFC Spindial サンプル コントロールをパッケージ化するタグです。  
  
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
  
 この場合、2 つのファイル、spindial.ocx および spindial.inf spindial.cab が含まれます。 次のコマンドは、キャビネット ファイルにビルドされます。  
  
```  
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf   
```  
  
 `-s 6144`パラメーターには、コード署名用キャビネットに領域が確保されます。  
  
### <a name="the-version-tag"></a>バージョン タグ  
 ここで注意、 `#Version` CAB ファイルで指定された情報で指定されたコントロールに適用されます、`CLASSID`のパラメーター、`<OBJECT>`タグ。  
  
 バージョンによっては、指定した、コントロールのダウンロードを強制することができます。 完全な仕様については、`OBJECT`タグを含む、`CODEBASE`パラメーターでは、参照を W3C を参照してください。  
  
##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> スクリプトと初期化の安全性をマークします。  
 Web ページで使用する ActiveX コントロールは、スクリプト作成と初期化実際には安全である場合の安全性としてマークする必要があります。 安全なコントロールはディスク IO を実行またはメモリやマシンのレジスタに直接アクセスされません。  
  
 コントロールは、スクリプトやレジストリを使用して初期化に対して安全としてマークできます。 変更`DllRegisterServer`コントロールをスクリプトと、レジストリに永続化の安全としてマークするには、次のようなエントリを追加します。 別の方法は、実装する`IObjectSafety`です。  
  
 安全なは、スクリプトを実行して、永続化を示すために、コントロールの Guid (グローバル一意識別子) を定義します。 安全にスクリプトを作成できるコントロールは、次のようにレジストリ エントリが表示されます。  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 永続的なデータから安全に初期化できるコントロールを永続化のようなレジストリ エントリを安全にマークされます。  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 次のようなエントリを追加 (コントロールの置換クラスの代わりに ID `{06889605-B8D0-101A-91F1-00608CEAD5B3}`) に次のクラス ID で、キーを関連付けるには。  
  
```  
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}   
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}   
```  
  
##  <a name="_core_licensing_issues"></a> ライセンスの問題  
 Web ページでライセンスされたコントロールを使用する場合、使用許諾契約書が、インターネット上の使用が使用をそのライセンス パッケージ ファイル (LPK) を作成することを確認する必要があります。  
  
 ライセンスされた ActiveX コントロールは読み込まれません正しく HTML ページにコントロールを使用して Internet Explorer を実行しているコンピューターのライセンスがない場合。 たとえば、ライセンスされたコントロールは、Visual C を使用してビルドされていた場合、コントロールを使用して、HTML ページが正常に読み込まコントロールの作成は、ライセンス情報が含まれていない限り、別のコンピューターには読み込まれませんが、コンピューター上。  
  
 ライセンスされた ActiveX コントロールを使用して、Internet Explorer で、コントロールのライセンスができることを確認する仕入先の使用許諾契約書を確認する必要があります。  
  
-   再配布  
  
-   インターネット上のコントロールの使用  
  
-   コードベース パラメーターの使用  
  
 ライセンスのないコンピューター上の HTML ページでライセンスされたコントロールを使用するには、ライセンス パッケージ ファイル (LPK) を生成する必要があります。 LPK ファイルには、HTML ページでライセンスされたコントロールの実行時ライセンスが含まれています。 LPK_TOOL 経由でこのファイルが生成されます。ActiveX SDK に付属している EXE です。 詳細については、MSDN Web サイトを参照してください。 [ http://msdn.microsoft.com](http://msdn.microsoft.com)です。  
  
#### <a name="to-create-an-lpk-file"></a>LPK ファイルを作成するには  
  
1.  LPK_TOOL を実行します。コントロールを使用するライセンスがあるコンピューター上の exe ファイル。  
  
2.  **ライセンス パッケージ Authoring Tool**  ダイアログ ボックスで、**利用可能なコントロール**リスト ボックスで、ライセンスされている ActiveX コントロールが HTML ページで使用され、をクリックをそれぞれ選択**追加**.  
  
3.  をクリックして**保存し、終了**LPK ファイルの名前を入力します。 LPK ファイルが作成され、アプリケーションを終了します。  
  
#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>HTML ページでライセンスされたコントロールを埋め込むには  
  
1.  HTML ページを編集します。 HTML ページで、挿入、\<オブジェクト > タグの前に、他のライセンス マネージャー オブジェクト\<オブジェクト > タグです。 ライセンス マネージャーは、Internet Explorer にインストールされている ActiveX コントロールです。 クラス ID は、以下に示します。 LPK ファイルの名前とパスをライセンス マネージャー オブジェクトの LPKPath プロパティを設定します。 HTML ページごとに 1 つだけ LPK ファイルことができます。  
  
 ```  
 <OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">  
 </OBJECT>  
 ```  
  
2.  挿入、\<オブジェクト > ライセンス マネージャー タグの後にライセンスされたコントロールのタグ。  
  
     たとえば、Microsoft マスク エディット コントロールを表示する HTML ページは、以下に示します。 最初のクラス ID がライセンス マネージャー コントロールに対する、ID は、マスク エディット コントロールの 2 番目のクラスです。 事前に作成した .lpk ファイルの相対パスをポイントするタグを変更し、コントロールのクラス ID を含むオブジェクトのタグを追加します。  
  
3.  挿入、\<埋め込む > NCompass ActiveX プラグインを使用する場合、LPK ファイルの属性です。  
  
     アクティブ ブラウザー有効になっている場合は、他のコントロールを表示することがあります: NCompass ActiveX プラグインを使用して Netscape など: 追加する必要があります、\<埋め込み > 構文を次に示すようです。  
  
 ```  
 <OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="maskedit.lpk">  
 
 <EMBED SRC = "maskedit.LPK">  
 
 </OBJECT>  
 <OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>  
 </OBJECT>  
 ```  
  
 コントロールのライセンスの詳細については、次を参照してください。 [ActiveX コントロール: ActiveX コントロールのライセンス](../mfc/mfc-activex-controls-licensing-an-activex-control.md)です。  
  
##  <a name="_core_signing_code"></a> コードの署名  
 コードのソースを識別するように設計されたコード署名および署名された後に、コードが変更されていないことを保証するためにします。 ブラウザーの安全性の設定によって、コードをダウンロードする前に、ユーザーを警告可能性があります。 ユーザーが特定の証明書の所有者またはものによって署名されたケースのコードが警告なしにダウンロードは信頼された企業を信頼する選択可能性があります。 コードは、改ざんを回避するデジタル署名します。  
  
 信頼の警告メッセージを表示することがなく、コントロールを自動的にダウンロードできるように、最終的なコードが署名を確認します。 コード署名する方法の詳細については、Authenticode ActiveX sdk のマニュアルを確認しを参照してください[CAB ファイルへの署名](http://msdn.microsoft.com/en-us/04d8b47a-8f1c-4b54-ab90-730fcdc03747)です。  
  
 信頼およびブラウザーの安全性レベル設定によって、署名した個人または会社を識別する証明書が表示されます。 安全性レベルは none、符号付きのコントロールの証明書の所有者が信頼されている場合や、証明書は表示されません。 参照してください[Internet Explorer ブラウザーの安全性レベルと動作を制御](#_core_internet_explorer_browser_safety_levels_and_control_behavior)詳細については、コントロールをダウンロードするかどうかと証明書の表示のブラウザーの安全性設定の決定にします。  
  
 署名されているために、デジタル署名の保証のコードは変更されていません。 コードのハッシュが取得され、証明書に埋め込まれます。 このハッシュ コードをダウンロードした後は、実行前に実行されるコードのハッシュと比較します。 Verisign などの企業では、コードの署名に必要なプライベートとパブリックのキーを指定できます。 ActiveX SDK は、MakeCert、テスト証明書を作成するためのユーティリティに付属します。  
  
##  <a name="_core_managing_the_palette"></a> パレットの管理  
 コンテナーがパレットを決定しをアンビエント プロパティとして使用できるように**DISPID_AMBIENT_PALETTE**です。 コンテナー (たとえば、Internet Explorer) は、ページ上のすべての ActiveX コントロールで、独自のパレットを決定するために使用するパレットを選択します。 これは、ディスプレイのちらつきを防止し、一貫した外観を示します。  
  
 オーバーライドする`OnAmbientPropertyChange`パレットを変更の通知を処理します。  
  
 オーバーライドする`OnGetColorSet`を色のパレットを描画するセットを返します。 コンテナーは、コントロールがパレットに対応するかを判断、戻り値を使用します。  
  
 OCX 96 ガイドラインについては、下にあるコントロールは常にバック グラウンドでパレットを実現する必要があります。  
  
 アンビエント palette プロパティを使用していない古いコンテナーは送信`WM_QUERYNEWPALETTE`と`WM_PALETTECHANGED`メッセージ。 オーバーライドする`OnQueryNewPalette`と`OnPaletteChanged`をこれらのメッセージを処理します。  
  
##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Internet Explorer ブラウザーの安全性レベルとコントロールの動作  
 ブラウザーでは、安全性レベルの場合、ユーザーによって構成可能なオプションがあります。 Web ページには、ユーザーのコンピューターに危害を及ぼす可能性がある可能性がありますのアクティブ コンテンツを含めることができます、ために、ブラウザーは安全性レベルのオプションを選択するユーザーを許可します。 ブラウザーには、安全性レベルが実装する方法、に応じて、コントロールは、ダウンロードできません可能性があります。 または証明書またはユーザーが実行時にコントロールをダウンロードするかどうか選択を許可する警告メッセージが表示されます。 高、中、低の安全性レベルの下にある Internet Explorer の ActiveX コントロールの動作は、以下に記載されています。  
  
### <a name="high-safety-mode"></a>高い安全性モード  
  
-   符号なしのコントロールはダウンロードされません。  
  
-   署名済みのコントロールは、信頼されていない場合、証明書に表示されます (ユーザーは、常に今後この証明書の所有者からコードを信頼するオプションを選択できます)。  
  
-   安全としてマークされているコントロールだけがスクリプトを実行または永続的なデータが含まれてはします。  
  
### <a name="medium-safety-mode"></a>中規模の安全性モード  
  
-   符号なしのコントロールをダウンロードする前に警告が表示されます。  
  
-   信頼されていない場合、証明書を署名済みのコントロールが表示されます。  
  
-   安全としてマークされていないコントロールでは、警告を表示します。  
  
### <a name="low-safety-mode"></a>低の安全性モード  
  
-   コントロールは、警告なしにダウンロードされます。  
  
-   スクリプトの作成と永続化警告なしに発生します。  
  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [MFC ActiveX コントロール: ActiveX コントロールのライセンス](../mfc/mfc-activex-controls-licensing-an-activex-control.md)

