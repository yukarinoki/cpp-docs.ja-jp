---
title: リンカー プロパティ ページ
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 2f2068c6c51fc6bf4e4104213e946e243fc6df2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336580"
---
# <a name="linker-property-pages"></a>リンカー プロパティ ページ

次のプロパティは、[**プロジェクト** > **プロパティ** > **の構成プロパティ] の** > **下にあります**。 リンカーの詳細については、「CL がリンカーオプションおよび[リンカーオプション](linker-options.md)[を呼び出す](cl-invokes-the-linker.md)」を参照してください。

## <a name="general-property-page"></a>[全般] プロパティ ページ

### <a name="output-file"></a>出力ファイル

[/OUT](out-output-file-name.md)オプションは、リンカーが作成するプログラムの既定の名前と場所をオーバーライドします。

### <a name="show-progress"></a>進行状況の表示

リンカーの進行状況メッセージを印刷します

**選択肢**

- **設定されていません**- 詳細はありません。
- **すべての進行状況メッセージを表示**する - すべての進行状況メッセージを表示します。
- **[検索されたライブラリの場合**] - 検索されたライブラリのみを示す進行状況メッセージが表示されます。
- **最適化されたリンク時の COMDAT 折りたたみについて**- 最適化されたリンク中の COMDAT 折りたたみに関する情報を表示します。
- **最適化されたリンク中に削除されたデータについて**- 最適化されたリンク中に削除された関数およびデータに関する情報を表示します。
- **SEH と互換性のないモジュールについて**- 安全な例外処理と互換性のないモジュールに関する情報を表示します。
- **マネージ コードに関連するリンカー アクティビティについて**- マネージ コードに関連するリンカー アクティビティに関する情報を表示します。

### <a name="version"></a>Version

[/VERSION](version-version-information.md)オプションは、.exe ファイルまたは .dll ファイルのヘッダーにバージョン番号を入れるリンカーに指示します。 DUMPBIN /HEADERS を使用して、オプションヘッダー値のイメージ・バージョン・フィールドを表示して **、/VERSION**の効果を確認します。

### <a name="enable-incremental-linking"></a>インクリメンタル リンクを有効にする

インクリメンタル リンクを有効にします。 ([/インクリメンタル](incremental-link-incrementally.md)、/インクリメンタル:いいえ)

### <a name="suppress-startup-banner"></a>著作権情報の非表示

[/NOLOGO](nologo-suppress-startup-banner-linker.md)オプションを指定すると、著作権に関するメッセージとバージョン番号が表示されなくなります。

### <a name="ignore-import-library"></a>インポート ライブラリの無視

このプロパティは、このビルドから生成された .lib 出力を依存プロジェクトにリンクしないようにリンカーに通知します。 ビルド時に .lib ファイルを生成しない .dll ファイルをプロジェクト システムで処理できます。 あるプロジェクトが DLL を生成する他のプロジェクトに依存している場合、プロジェクト システムでは子プロジェクトによって生成される .lib ファイルを自動的にリンクします。 COM DLL またはリソースのみの DLL を生成するプロジェクトでは、これらの DLL には意味のあるエクスポートがないため、このプロパティは不要な場合があります。 DLL にエクスポートがない場合、リンカーは .lib ファイルを生成しません。 エクスポート .lib ファイルが存在せず、プロジェクト システムが存在しない DLL とリンクするようにリンカーに指示した場合、リンクは失敗します。 この問題を解決するには、**[インポート ライブラリの無視]** プロパティを使用します。 **[はい**] に設定すると、プロジェクト システムは .lib ファイルの有無を無視し、このプロジェクトに依存するすべてのプロジェクトが存在しない .lib ファイルとリンクしないようにします。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>」を参照してください。

### <a name="register-output"></a>出力の登録

.dll プロジェクトでのみ有効なビルド出力で `regsvr32.exe /s $(TargetPath)` を実行します。 .exe プロジェクトでは、このプロパティは無視されます。 .exe 出力を登録するには、構成にビルド後のイベントを設定し、登録済みの .exe ファイルに必要なカスタム登録を行います。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>」を参照してください。

### <a name="per-user-redirection"></a>ユーザーごとのリダイレクト

Visual Studio の登録はこれまで、HKEY_CLASSES_ROOT (HKCR) で行われてきました。 Windows Vista 以降のオペレーティング システムでは、HKCR にアクセスするには、特権モードで Visual Studio を実行する必要があります。 開発者は常に管理者特権モードで実行する必要はありませんが、登録を使用する必要があります。 ユーザーごとのリダイレクトを使用すると、管理者特権モードで実行しなくても登録できます。

ユーザーごとのリダイレクトは、HKCR への書き込みが HKEY\_CURRENT\_USER (HKCU) にリダイレクトされるように強制します。 ユーザーごとのリダイレクトをオフにすると、プログラムが HKCR への書き込みを試行するときに[プロジェクト ビルド エラー PRJ0050](../../error-messages/tool-errors/project-build-error-prj0050.md) が発生する場合があります。

### <a name="additional-library-directories"></a>追加のライブラリ ディレクトリ

環境のライブラリ パスをユーザーがオーバーライドできるようにします。 ([/LIBPATH](libpath-additional-libpath.md):フォルダ)

### <a name="link-library-dependencies"></a>ライブラリ依存関係のリンク

依存プロジェクトによって生成された .lib ファイルをリンクするかどうかを指定します。 通常、.lib ファイル内でリンクする必要がありますが、特定の DLL には当てはまらない場合があります。

また、ファイル名と相対パス (たとえば "..\\..\MyLibProject\MyObjFile.obj") によって .obj ファイルを指定できます。 obj ファイルのソース コードがプリコンパイル済みヘッダー (pch.h など) を#includes場合、pch.obj ファイルは MyObjFile.obj と同じフォルダーに格納されます。さらに、追加の依存関係として pch.obj を追加する必要があります。

### <a name="use-library-dependency-inputs"></a>ライブラリ依存関係の入力の使用

プロジェクトの依存関係のライブラリ出力にリンクするときに、ライブラリ ファイル自体ではなく、ライブラリャーツールへの入力を使用するかどうかを指定します。 大規模なプロジェクトでは、依存プロジェクトによって .lib ファイルが生成される場合、インクリメンタル リンクは無効にされています。 .lib ファイルを生成する依存プロジェクトが多数存在する場合、アプリケーションのビルドに長時間を要する場合があります。 このプロパティを **[はい**] に設定すると、依存プロジェクトによって生成された .lib ファイルの .obj ファイル内のプロジェクト システムリンクが設定され、インクリメンタル リンクが有効になります。

**[全般**リンカー] プロパティ ページにアクセスする方法については[、「Visual Studio で C++ コンパイラとビルド プロパティを設定](../working-with-project-properties.md)する」を参照してください。

### <a name="link-status"></a>リンクの状態

リンクの完了率を示す進行状況インジケーターをリンカーに表示するかどうかを指定します。 デフォルトでは、このステータス情報は表示されません。 ([/LTCG](ltcg-link-time-code-generation.md):ステータス|LTCG:ノーステータス)

### <a name="prevent-dll-binding"></a>DLL のバインドを禁止する

[/ALLOWBIND](allowbind-prevent-dll-binding.md):NO は、イメージのバインドが許可されていないことを Bind.exe に示す DLL のヘッダーにビットを設定します。 DLL がデジタル署名されている場合はバインドしないほうがよいでしょう (バインドによって署名が無効になる)。

### <a name="treat-linker-warning-as-errors"></a>リンカーの警告をエラーとして扱う

[/WX](wx-treat-linker-warnings-as-errors.md)は、リンカーが警告を生成した場合に出力ファイルを生成しません。

### <a name="force-file-output"></a>強制ファイル出力

[/FORCE](force-force-file-output.md)オプションは、シンボルが参照されていても定義されていない場合、または定義されていない場合でも.exe ファイルまたは DLL を作成するようにリンカーに指示します。 無効な .exe ファイルが作成される可能性があります。

**選択肢**

- **有効**- 引数を指定しない /FORCE は、複数の引数と未解決の両方を意味します。
- **[定義されたシンボルのみで乗算]** - LINK がシンボルの定義を複数見つけた場合でも、出力ファイルを作成するには /FORCE:MULTIPLE を使用します。
- **未定義シンボルのみ**- LINK が未定義シンボルを見つけるかどうかに関係なく、出力ファイルを作成するには/FORCE:UNRESOLVED を使用します。 /FORCE:エントリ ポイント シンボルが未解決の場合は、UNRESOLVED は無視されます。

### <a name="create-hot-patchable-image"></a>ホット パッチ可能なイメージを作成する

ホットパッチ用のイメージを準備します。

**選択肢**

- **[有効]** - ホットパッチ用のイメージを準備します。
- **X86 イメージのみ**- ホットパッチ用に X86 イメージを準備します。
- **X64 イメージのみ**- ホットパッチ用の X64 イメージを準備します。
- **イタニウム画像のみ**- ホットパッチ用のイタニウム画像を準備します。

### <a name="specify-section-attributes"></a>セクション属性の指定

[/SECTION](section-specify-section-attributes.md)オプションは、セクションの属性を変更し、セクションの .obj ファイルがコンパイルされたときに設定された属性をオーバーライドします。

## <a name="input-property-page"></a>入力プロパティ ページ

### <a name="additional-dependencies"></a>追加の依存ファイル

リンク コマンド ラインに追加する追加項目を*指定します。*

### <a name="ignore-all-default-libraries"></a>[すべての既定ライブラリを無視]

[/NODEFAULTLIB](nodefaultlib-ignore-libraries.md)オプションは、外部参照を解決するときに検索するライブラリのリストから 1 つ以上のデフォルト ライブラリを削除するようにリンカーに指示します。

### <a name="ignore-specific-default-libraries"></a>特定の既定のライブラリの無視

無視する既定のライブラリの名前を 1 つ以上指定します。 複数のライブラリをセミコロンで区切ります。 (/ノデフォルトリブ:[名前、名前、.])

### <a name="module-definition-file"></a>モジュール定義ファイル

[/DEF](def-specify-module-definition-file.md)オプションは、モジュール定義ファイル (.def) をリンカーに渡します。 LINK には 1 つの .def ファイルしか指定できません。

### <a name="add-module-to-assembly"></a>アセンブリにモジュールを追加

[/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)オプションを使用すると、アセンブリにモジュール参照を追加できます。 モジュールの型情報は、モジュール参照を追加したアセンブリ プログラムでは使用できません。 ただし、モジュール内の型情報は、アセンブリを参照するすべてのプログラムで使用できます。

### <a name="embed-managed-resource-file"></a>マネージ リソース ファイルの埋め込み

[/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)は、出力ファイルにリソース ファイルを埋め込みます。

### <a name="force-symbol-references"></a>シンボル参照の強制

[/INCLUDE](include-force-symbol-references.md)オプションは、指定したシンボルをシンボル テーブルに追加するようにリンカーに指示します。

### <a name="delay-loaded-dlls"></a>読み込まれた DLL の遅延

[/DELAYLOAD](delayload-delay-load-import.md)オプションは、DLL の読み込みが遅延します。 dll 名は、読み込みを遅延する DLL を指定します。

### <a name="assembly-link-resource"></a>アセンブリ リンク リソース

[/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)オプションは、出力ファイル内の .NET Framework リソースへのリンクを作成します。リソース ファイルは出力ファイルに格納されません。

## <a name="manifest-file-property-page"></a>マニフェスト ファイルプロパティ ページ

### <a name="generate-manifest"></a>マニフェストを生成する

[/MANIFEST](manifest-create-side-by-side-assembly-manifest.md)は、リンカーがサイド バイ サイド のマニフェスト ファイルを作成することを指定します。

### <a name="manifest-file"></a>マニフェスト ファイル

[/MANIFESTFILE](manifestfile-name-manifest-file.md)では、マニフェスト ファイルの既定の名前を変更できます。 マニフェスト ファイルの既定の名前は、.manifest が付加されたファイル名です。

### <a name="additional-manifest-dependencies"></a>追加のマニフェスト依存関係

[/MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md)を使用すると、マニフェスト ファイルの依存関係セクションに配置される属性を指定できます。

### <a name="allow-isolation"></a>分離を許可する

マニフェスト検索の動作を指定します。 ([/許可分離](allowisolation-manifest-lookup.md):いいえ)

### <a name="enable-user-account-control-uac"></a>ユーザー アカウント制御 (UAC) を有効にする

ユーザー アカウント制御を有効にするかどうかを指定します。  ([/マニフェストアック](manifestuac-embeds-uac-information-in-manifest.md),/マニフェスト:いいえ)

### <a name="uac-execution-level"></a>UAC 実行レベル

ユーザー アカウント制御で実行する場合のアプリケーションに対して要求された実行レベルを指定します。  (/マニフェスト:レベル=[値])

**選択肢**

- **asInvoker** - UAC 実行レベル: 呼び出し者として。
- **最高利用可能 -** UAC実行レベル: 最高の利用可能です。
- **必要管理者**- UAC 実行レベル: 管理者が必要です。

### <a name="uac-bypass-ui-protection"></a>UAC バイパス UI 保護

デスクトップ上の他のウィンドウのユーザー インターフェイス保護レベルをバイパスするかどうかを指定します。  アクセシビリティ アプリケーションの場合にのみ、このプロパティを [はい] に設定します。  ([/マニフェストアック](manifestuac-embeds-uac-information-in-manifest.md):uiAccess=[true | 偽] ) )

## <a name="debugging-property-page"></a>[デバッグ] プロパティ ページ

### <a name="generate-debug-info"></a>デバッグ情報の生成

このオプションを使用すると、.exe ファイルまたは DLL のデバッグ情報を作成できます。

**選択肢**

- **いいえ**- デバッグ情報を生成しません。
- **デバッグ情報の生成**- Microsoft シンボル サーバーへの配布に最適な完全なプログラム データベース (PDB) を作成します。
- **高速リンクに最適化されたデバッグ情報を生成**- 編集-リンク/デバッグサイクルに最適なプログラムデータベース(PDB)を生成します。
- **共有と公開に最適化されたデバッグ情報の生成**- 編集-リンク/デバッグサイクルに最適なプログラムデータベース(PDB)を生成します。

### <a name="generate-program-database-file"></a>プログラム データベース ファイルの生成

既定では[、/DEBUG](debug-generate-debug-info.md)が指定されると、リンカーはデバッグ情報を保持するプログラム データベース (PDB) を作成します。 PDB の既定のファイル名には、プログラムの基本名と拡張子 .pdb が付いています。

### <a name="strip-private-symbols"></a>プライベート シンボルを削除する

[/PDBSTRIPPED](pdbstripped-strip-private-symbols.md)オプションは、PDB ファイル (/DEBUG、/Z7、/Zd、または /Zi) を生成するコンパイラまたはリンカー オプションのいずれかを使用してプログラム イメージをビルドするときに、2 番目のプログラム データベース (PDB) ファイルを作成します。

### <a name="generate-map-file"></a>マップ ファイルの生成

[/MAP](map-generate-mapfile.md)オプションは、マップファイルを作成するようにリンカーに指示します。

### <a name="map-file-name"></a>マップ ファイル名

マップ ファイルのユーザー指定の名前。 既定の名前を置き換えます。

### <a name="map-exports"></a>マップエクスポート

[/MAPINFO](mapinfo-include-information-in-mapfile.md)オプションは、/MAP オプションを指定すると作成されるマップファイルに指定された情報を含むようにリンカーに指示します。 EXPORTS は、エクスポートされた関数を含むようにリンカーに指示します。

### <a name="debuggable-assembly"></a>デバッグ可能なアセンブリ

[/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)はデバッグ情報の追跡を使用して、Debuggable属性属性を生成し、JIT 最適化を無効にします。

## <a name="system-property-page"></a>システム プロパティ ページ

### <a name="subsystem"></a>サブシステム

[/SUBSYSTEM](subsystem-specify-subsystem.md)オプションは、オペレーティング システムに .exe ファイルの実行方法を指示します。 サブシステムの選択は、リンカーが選択するエントリ ポイント シンボル (またはエントリ ポイント関数) に影響します。

**選択肢**

- **設定されていません**- サブシステムが設定されていません。
- **コンソール**- Win32 文字モード アプリケーション。 コンソール アプリケーションには、オペレーティング システムによってコンソールが与えられます。 main または wmain が定義されている場合は、CONSOLE がデフォルトです。
- **Windows** - アプリケーションは、おそらくユーザーと対話するための独自のウィンドウを作成するため、コンソールを必要としません。 WinMain または wWinMain が定義されている場合は、WINDOWS が既定です。
- **ネイティブ**- Windows NT 用のデバイス ドライバ。 /DRIVER:WDM が指定されている場合、既定値は NATIVE です。
- **EFI アプリケーション**- EFI アプリケーション。
- **EFI ブート サービス ドライバー** - EFI ブート サービス ドライバー。
- **EFI ROM** - EFI ROM。
- **EFI ランタイム**- EFI ランタイム。
- **POSIX** - Windows NT の POSIX サブシステムで実行されるアプリケーション。

### <a name="minimum-required-version"></a>最低限必要なバージョン

サブシステムに最低限必要なバージョンを指定します。 引数には、0 ～ 65535 の範囲の 10 進数を指定します。

### <a name="heap-reserve-size"></a>ヒープリザーブサイズ

仮想メモリ内のヒープ割り当てサイズの合計を指定します。 デフォルトは 1 MB です。    ([/ヒープ](heap-set-heap-size.md): リザーブ)

### <a name="heap-commit-size"></a>ヒープコミットサイズ

物理メモリのヒープ割り当てサイズの合計を指定します。 デフォルトは 4 KB です。    ([/ヒープ](heap-set-heap-size.md):予約、コミット)

### <a name="stack-reserve-size"></a>[スタックのサイズの設定]

仮想メモリ内のスタック割り当て合計サイズを指定します。 デフォルトは 1 MB です。     ([/スタック](stack-stack-allocations.md): 予約)

### <a name="stack-commit-size"></a>[スタックのコミット サイズ]

物理メモリのスタック割り当て合計サイズを指定します。 デフォルトは 4 KB です。     ([/スタック](stack-stack-allocations.md): 予約、コミット)

### <a name="enable-large-addresses"></a>大きなアドレスを有効にする

[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)オプションは、アプリケーションが 2 ギガバイトを超えるアドレスを処理できることをリンカーに通知します。 既定では、リンカーラインで /LARGEADDRESSAWARE が指定されていない場合は、/LARGEADDRESSAWARE:NO が有効になります。

### <a name="terminal-server"></a>ターミナル サーバー

[/TSAWARE](tsaware-create-terminal-server-aware-application.md)オプションは、プログラム イメージのオプション ヘッダーの IMAGE_OPTIONAL_HEADER Dll 特性フィールドにフラグを設定します。 このフラグが設定されると、ターミナル サーバーはアプリケーションに特定の変更を加えなくなります。

### <a name="swap-run-from-cd"></a>スワップはCDから実行します

[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md)オプションは、まずリンカー出力をスワップ ファイルにコピーし、そこからイメージを実行するようにオペレーティング システムに指示します。 このオプションは、Windows NT 4.0 以降の機能です。 **CD**を指定すると、オペレーティング システムはリムーバブル ディスク上のイメージをページ ファイルにコピーし、読み込みます。

### <a name="swap-run-from-network"></a>ネットワークからスワップ実行

[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md)オプションは、まずリンカー出力をスワップ ファイルにコピーし、そこからイメージを実行するようにオペレーティング システムに指示します。 このオプションは、Windows NT 4.0 以降の機能です。 **NET**を指定すると、オペレーティング システムは最初にネットワークからスワップ ファイルにバイナリ イメージをコピーし、そこから読み込みます。 このオプションは、ネットワーク上でアプリケーションを実行する場合に便利です。

### <a name="driver"></a>Driver

Windows NT カーネル モード ドライバをビルドするには[、/DRIVER](driver-windows-nt-kernel-mode-driver.md)リンカー オプションを使用します。

**選択肢**

- **設定されていません**- 既定のドライバー設定。
- **ドライバー** - ドライバー
- **UP のみ**- /DRIVER:UPONLY を指定すると、リンカーは、IMAGE_FILE_UP_SYSTEM_ONLY ビットを出力ヘッダーの特性に追加し、それがユニプロセッサ (UP) ドライバーであることを指定します。 オペレーティング システムは、マルチプロセッサ (MP) システムでの UP ドライバの読み込みを拒否します。
- **WDM** - /DRIVER:WDM は、オプションのヘッダーの Dll特性フィールドにIMAGE_DLLCHARACTERISTICS_WDM_DRIVERビットを設定するリンカーを発生させます。

## <a name="optimization-property-page"></a>最適化プロパティ ページ

### <a name="references"></a>関連項目

[/OPT](opt-optimizations.md):REF は、参照されていない関数やデータを削除しますが、/OPT:NOREF は参照されていない関数やデータを保持します。

### <a name="enable-comdat-folding"></a>[COMDAT の圧縮]

[/OPT](opt-optimizations.md):ICF\[=反復] を使用して、同一の COMDAT 折りたたみを実行します。

### <a name="function-order"></a>関数の順序

[/ORDER](order-put-functions-in-order.md)オプションは、特定の COMDAT をあらかじめ決められた順序でイメージに配置することによって、プログラムを最適化するよう LINK に指示します。 LINK は、イメージ内の各セクション内の指定された順序で関数を配置します。

### <a name="profile-guided-database"></a>ガイド付きデータベースのプロファイル

ガイド付き最適化のプロファイルを作成するには、.pgd ファイルを指定します。 ([/PGD](pgd-specify-database-for-profile-guided-optimizations.md))

### <a name="link-time-code-generation"></a>リンク時のコード生成

リンク時のコード生成を指定します。 ([/LTCG](ltcg-link-time-code-generation.md))

**選択肢**

- **デフォルト**- デフォルト LTCG 設定。
- **高速リンク時間コード生成の使用**- [/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)でのリンク時コード生成の使用。
- **[リンク時コード生成を使用**する -[リンク時コード生成を使用]](ltcg-link-time-code-generation.md)
- **ガイド付き最適化のプロファイル - :PGINSTRUMENT**で[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)を使用します。
- **ガイド付き最適化のプロファイル - 最適化**- リンカーが、インストルメント化されたバイナリを実行した後に作成されたプロファイル データを使用して最適化されたイメージを作成するように指定します。
- **ガイド付き最適化のプロファイル - 更新**- :PGINSTRUMENT フェーズで指定された内容から、入力ファイルのリストを追加または変更できます。

## <a name="embedded-idl-property-page"></a>埋め込み IDL プロパティ ページ

### <a name="midl-commands"></a>MIDL コマンド

MIDL コマンド ライン オプションを指定します。 ([/MIDL](midl-specify-midl-command-line-options.md):@responsefile)

### <a name="ignore-embedded-idl"></a>埋め込み IDL を無視する

[/IGNOREIDL](ignoreidl-don-t-process-attributes-into-midl.md)オプションは、ソース コード内の IDL 属性を .idl ファイルに処理しないように指定します。

### <a name="merged-idl-base-file-name"></a>マージされた IDL ベース ファイル名

[/IDLOUT](idlout-name-midl-output-files.md)オプションは、.idl ファイルの名前と拡張子を指定します。

### <a name="type-library"></a>タイプ ライブラリ

[/TLBOUT](tlbout-name-dot-tlb-file.md)オプションは、.tlb ファイルの名前と拡張子を指定します。

### <a name="typelib-resource-id"></a>タイプリブリソースID

リンカーによって生成されたタイプ ライブラリのリソース ID を指定できます。 ([/TLBID](tlbid-specify-resource-id-for-typelib.md):id)

## <a name="windows-metadata-property-page"></a>Windows メタデータ プロパティ ページ

### <a name="generate-windows-metadata"></a>Windows メタデータの生成

Windows メタデータの生成を有効または無効にします。

**選択肢**

- **はい**- Windows メタデータ ファイルの生成を有効にします。
- **いいえ**- Windows メタデータ ファイルの生成を無効にします。

### <a name="windows-metadata-file"></a>Windows メタデータ ファイル

[/WINMDFILE](winmdfile-specify-winmd-file.md)オプション スイッチ。

### <a name="windows-metadata-key-file"></a>Windows メタデータ キー ファイル

Windows メタデータに署名するキーまたはキーのペアを指定します。 ([/WINMDKEY ファイル](winmdkeyfile-specify-winmd-key-file.md):ファイル名)

### <a name="windows-metadata-key-container"></a>Windows メタデータ キー コンテナー

Windows メタデータに署名するキー コンテナーを指定します。 ([/ウィンムドキーコンテナ](winmdkeycontainer-specify-key-container.md):名前)

### <a name="windows-metadata-delay-sign"></a>Windows メタデータ遅延サイン

Windows メタデータに部分的に署名します。 Windows メタデータにパブリック キーのみを配置する場合は[、/WINMDDELAYSIGN](winmddelaysign-partially-sign-a-winmd.md)を使用します。 デフォルトは /WINMDDELAYSIGN:NO です。

## <a name="advanced-property-page"></a>[詳細プロパティ] ページ

### <a name="entry-point"></a>エントリ ポイント

[/ENTRY](entry-entry-point-symbol.md)オプションは、.exe ファイルまたは DLL の開始アドレスとしてエントリ ポイント関数を指定します。

### <a name="no-entry-point"></a>エントリ ポイントなし

リソースのみの DLL を作成するには[、/NOENTRY](noentry-no-entry-point.md)オプションが必要です。このオプションを使用して、LINK が参照を`_main`DLL にリンクしないようにします。

### <a name="set-checksum"></a>チェックサムを設定する

[/RELEASE](release-set-the-checksum.md)オプションは、.exe ファイルのヘッダーにチェックサムを設定します。

### <a name="base-address"></a>ベース アドレス

プログラムのベース アドレスを設定します。 ([/BASE](base-base-address.md):{アドレス\[、サイズ] |@filename、キー})

### <a name="randomized-base-address"></a>ランダム化ベースアドレス

ランダム化ベースアドレス。 ([/ダイナミックベース](dynamicbase-use-address-space-layout-randomization.md)\[:いいえ])

### <a name="fixed-base-address"></a>固定ベース アドレス

指定のベース アドレスだけに読み込まれるプログラムを作成します。 ([/固定](fixed-fixed-base-address.md)\[:いいえ])

### <a name="data-execution-prevention-dep"></a>データ実行防止 (DEP)

実行可能ファイルを、Windows データ実行防止機能と互換性のあるテスト済みとしてマークします。 ([/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)\[:いいえ])

### <a name="turn-off-assembly-generation"></a>アセンブリ生成をオフにする

[/NOASSEMBLY](noassembly-create-a-msil-module.md)オプションは、.NET Framework アセンブリを使用せずに、現在の出力ファイルのイメージを作成するようにリンカーに指示します。

### <a name="unload-delay-loaded-dll"></a>アンロード遅延読み込み DLL

**UNLOAD**修飾子は、DLL の明示的なアンロードをサポートする遅延読み込みヘルパー関数を指示します。 ([/遅延](delay-delay-load-import-settings.md): アンロード)

### <a name="nobind-delay-loaded-dll"></a>バインド遅延読み込み DLL

**NOBIND**修飾子は、最終イメージにバインド可能な IAT を含まないことをリンカーに指示します。 既定では、遅延読み込みされる DLL に対してバインドできる IAT が作成されます。 ([/遅延](delay-delay-load-import-settings.md): NOBIND)

### <a name="import-library"></a>インポート ライブラリ

既定のインポート ライブラリ名をオーバーライドします。 ([/IMPLIB](implib-name-import-library.md):ファイル名)

### <a name="merge-sections"></a>セクションのマージ

[/MERGE](merge-combine-sections.md)オプションは、最初のセクション (from) と 2 番目のセクション (to) を結合し、結果のセクションに名前を付ける。 たとえば、/マージ:.rdata=.text。

### <a name="target-machine"></a>ターゲットマシン

[/MACHINE](machine-specify-target-platform.md)オプションは、プログラムのターゲット プラットフォームを指定します。

**選択肢**

- **設定されていません**
- **マシンアーム**
- **マシンアーム64**
- **マシンEBC**
- **マシンIA64**
- **マシンミップス**
- **マシンミップス16**
- **マシンミプスフプ**
- **マシンミプスフプ16**
- **マシンSH4**
- **マシンサム**
- **マシンX64**
- **マシンX86**

### <a name="profile"></a>プロファイル

パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。 設定する必要があります。[/DEBUG](debug-generate-debug-info.md) ([/プロファイル](profile-performance-tools-profiler.md))

### <a name="clr-thread-attribute"></a>CLR スレッド属性

CLR プログラムのエントリ ポイントのスレッド属性を明示的に指定します。

**選択肢**

- **MTA スレッド属性**- プログラムのエントリ ポイントに MTAThreadAttribute 属性を適用します。
- **STA スレッド属性**- プログラムのエントリ ポイントに STAThreadAttribute 属性を適用します。
- **既定のスレッド化属性**- [/CLRTHREADATTRIBUTE](clrthreadattribute-set-clr-thread-attribute.md)を指定しない場合と同じです。 共通言語ランタイム (CLR) に既定のスレッド属性を設定できるようにします。

### <a name="clr-image-type"></a>CLR イメージの種類

CLR イメージの種類 (IJW、純粋、または安全) を設定します。

**選択肢**

- **IJW イメージを強制する**
- **フォースピュアILイメージ**
- **強制安全なILイメージ**
- **既定のイメージの種類**

### <a name="key-file"></a>キー ファイル

アセンブリに署名するキーまたはキーのペアを指定します。 ([/キーファイル](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md):ファイル名)

### <a name="key-container"></a>キー コンテナ

アセンブリに署名するキー コンテナーを指定します。 ([/キーコンテナ](keycontainer-specify-a-key-container-to-sign-an-assembly.md):名前)

### <a name="delay-sign"></a>遅延標識

アセンブリに部分的に署名します。 アセンブリ内に公開キーだけを配置する場合は[、/DELAYSIGN](delaysign-partially-sign-an-assembly.md)を使用します。 デフォルトは /DELAYSIGN:NO です。

### <a name="clr-unmanaged-code-check"></a>CLR アンマネージ コード チェック

[/CLRUNMANAGEDCODECHECK](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md)は、リンカーがマネージ コードからネイティブ DLL への呼び出しをリンカーで生成した PInvoke に適用するかどうかを指定します。

### <a name="error-reporting"></a>[エラー報告]

内部コンパイラ エラー (ICE) 情報を Visual C++ チームに直接報告できます。

**選択肢**

- **プロンプト即時**- 即座にプロンプトを出します。
- **次のログインのキュー** - 次のログインのキュー。
- **エラー 報告の送信**- エラー レポートを送信します。
- **エラー レポートなし**- エラー レポートなし。

### <a name="sectionalignment"></a>SectionAlignment

[/ALIGN](align-section-alignment.md)オプションは、プログラムの線形アドレス空間内の各セクションの配置を指定します。 number 引数はバイト単位で、2 の累乗でなければなりません。

### <a name="preserve-last-error-code-for-pinvoke-calls"></a>PInvoke 呼び出しの最後のエラー コードを保持する

[/CLRSUPPORTLASTERROR](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)は、既定でオンになって、/clr でコンパイルされたコードから DLLS のネイティブ関数を呼び出すことができる P/Invoke 機構を通じて呼び出される関数の最後のエラー コードを保持します。

**選択肢**

- **有効に**する - CLR サポートラストエラーを有効にします。
- **無効 -** CLR サポートラストエラーを無効にします。
- **システム DLL のみ**- システム DLL の場合にのみ、CLRSupportLastError を有効にします。

### <a name="image-has-safe-exception-handlers"></a>イメージに安全な例外ハンドラがある

[/SAFESEH](safeseh-image-has-safe-exception-handlers.md)を指定すると、リンカーはイメージの安全な例外ハンドラーのテーブルを生成できる場合にのみイメージを生成します。 このテーブルは、どの例外ハンドラーがイメージに対して有効であるかをオペレーティング システムに指定します。
