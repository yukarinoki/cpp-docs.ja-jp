---
description: 詳細については、「方法:/clr に移行する」を参照してください。
title: '方法: -clr に移行する'
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- upgrading Visual C++ applications, /clr compiler option
- compiling native code [C++]
- interoperability [C++], /clr compiler option
- interop [C++], /clr compiler option
- migration [C++], /clr compiler option
- /clr compiler option [C++], porting to
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
ms.openlocfilehash: 39853f755074a4999f39f9e04445234abfbe93b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286398"
---
# <a name="how-to-migrate-to-clr"></a>方法: /clr に移行する

このトピックでは、ネイティブコードを **/clr** でコンパイルするときに発生する問題について説明します (詳細については、「 [/Clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md) 」を参照してください)。 **/clr** を使用すると、ネイティブ c++ コードを呼び出し、他のネイティブ c++ コードに加えて .net アセンブリから呼び出すことができます。 **/Clr** でコンパイルする利点の詳細については、「[混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)」と「[ネイティブと .net の相互運用性](../dotnet/native-and-dotnet-interoperability.md)」を参照してください。

## <a name="known-issues-compiling-library-projects-with-clr"></a>/clr でライブラリ プロジェクトをコンパイルする場合の既知の問題

Visual Studio には、ライブラリプロジェクトを **/clr** でコンパイルするときの既知の問題がいくつか含まれています。

- コードでは、 [CRuntimeClass:: FromName](../mfc/reference/cruntimeclass-structure.md#fromname)を使用して実行時に型を照会することができます。 ただし、型が ( **/clr** でコンパイルされた) MSIL .dll 内にある場合、の呼び出しは、 `FromName` 静的コンストラクターがマネージ .dll で実行される前に発生した場合に失敗することがあります (コードがマネージ dll 内で実行された後に FromName 呼び出しが発生した場合は、この問題は発生しません)。 この問題を回避するには、マネージド静的コンストラクターを強制的に構築します。それには、マネージド .dll で関数を定義してエクスポートし、その関数をネイティブ MFC アプリケーションから呼び出します。 次に例を示します。

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>Visual C++ でのコンパイル

プロジェクト内の任意のモジュールで **/clr** を使用する前に、最初に Visual Studio 2010 でネイティブプロジェクトをコンパイルしてリンクします。

次の手順を順番に実行すると、 **/clr** コンパイルへの最も簡単なパスが提供されます。 これらの手順では、手順ごとにプロジェクトをコンパイルして実行することが重要です。

### <a name="versions-prior-to-visual-studio-2003"></a>Visual Studio 2003 より前のバージョン

Visual studio 2003 より前のバージョンから Visual Studio 2010 にアップグレードする場合、Visual Studio 2003 での C++ 標準準拠の強化に関連するコンパイラエラーが表示されることがあります。

### <a name="upgrading-from-visual-studio-2003"></a>Visual Studio 2003 からのアップグレード

Visual studio 2003 でビルドされた以前のプロジェクトは、Visual Studio で ANSI/ISO 準拠といくつかの重大な変更が向上したため、最初に **/clr** を使用せずにコンパイルする必要があります。 最も注意が必要な変更は、 [CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)です。 CRT を使用するコードでは、廃止警告が生成される可能性があります。 これらの警告は抑制できますが、新しい [セキュリティが強化されたバージョンの CRT 関数](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) に移行することをお勧めします。これは、セキュリティが向上し、コード内のセキュリティの問題が明らかになる可能性があるためです。

### <a name="upgrading-from-managed-extensions-for-c"></a>C++ マネージド拡張からのアップグレード

Visual Studio 2005 以降、Managed Extensions for C++ で記述されたコードは **/clr** でコンパイルされません。

## <a name="convert-c-code-to-c"></a>C コードから C++ への変換

Visual Studio は C ファイルをコンパイルしますが、 **/clr** コンパイルのために C++ に変換する必要があります。 実際のファイル名を変更する必要はありません。 **/tp** を使用できます (「 [/tc、/tp、/tc、/Tp (ソースファイルの種類を指定する)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md)」を参照してください)。C++ のソースコードファイルは **/clr** に必要ですが、オブジェクト指向パラダイムを使用するようにコードを再指定する必要はありません。

C コードは、C++ ファイルとしてコンパイルするときは変更を必要とする可能性があります。 C++ の型保証の規則は厳密なので、型の変換はキャストで明示的に行う必要があります。 たとえば、malloc は void ポインターを返しますが、キャストによる C では任意の型のポインターに割り当てることができます。

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

また C++ では関数ポインターの型も厳密に保証されているので、次のような C コードは変更が必要です。 C++ では、 **`typedef`** 関数ポインター型を定義するを作成し、その型を使用して関数ポインターをキャストすることをお勧めします。

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

また C++ では、関数を参照したり呼び出すには、その前にプロトタイプを作成するか完全に定義する必要があります。

C++ でキーワードになる C コードで使用される識別子 (、、、、、など) は、 **`virtual`** **`new`** 名前を **`delete`** **`bool`** **`true`** **`false`** 変更する必要があります。 これは一般的に、単純な検索置換操作だけで行うことができます。

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>プロジェクト設定の再構成

Visual Studio 2010 でプロジェクトをコンパイルして実行した後、既定の構成を変更するのではなく、新しいプロジェクト構成を **/clr** 用に作成する必要があります。 **/clr** は一部のコンパイラオプションと互換性がなく、個別の構成を作成することで、プロジェクトをネイティブまたはマネージとしてビルドできます。 /Clr **が** [プロパティページ] ダイアログボックスで選択されている場合、 **/clr** と互換性のないプロジェクト設定は無効になります ( **/clr** を後から選択解除した場合、無効なオプションは自動的には復元されません)。

### <a name="create-new-project-configurations"></a>新しいプロジェクト構成の作成

[**新しいプロジェクト構成] ダイアログボックス** の [**設定のコピー元**] オプションを使用して、既存のプロジェクト設定に基づいてプロジェクト構成を作成することができます ([**ビルド**  >  **Configuration Manager** の  >  **アクティブソリューション構成** の  >  **新規** 作成)。 これを、デバッグ構成に対して 1 回、リリース構成に対して 1 回実行してください。 その後の変更は、元のプロジェクト構成をそのままにして、 **/clr** 固有の構成にのみ適用できます。

カスタム ビルド規則を使用するプロジェクトには、特別な注意が必要な場合があります。

この手順は、メイクファイルを使用するプロジェクトにとって別の意味があります。 この場合、別のビルドターゲットを構成することも、元ののコピーから **/clr** コンパイルに固有のバージョンを作成することもできます。

### <a name="change-project-settings"></a>プロジェクトの設定の変更

/clr [(共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)に関する説明に従って、開発環境で **/clr** を選択できます。 既に説明したように、この手順によって競合するプロジェクト設定は自動的に無効になります。

> [!NOTE]
> マネージライブラリまたは web サービスプロジェクトを Visual Studio 2003 からアップグレードすると、[**コマンドライン**] プロパティページに **/zl** コンパイラオプションが追加されます。 これによって LNK2001 が発生します。 [**コマンドライン**] プロパティページから **/zl** を削除して解決します。 詳細については、「 [/zl (既定のライブラリ名の省略)](../build/reference/zl-omit-default-library-name.md) 」および「 [コンパイラとビルドプロパティの設定](../build/working-with-project-properties.md) 」を参照してください。 または、msvcrt.dll と msvcmrt.lib をリンカーの [ **追加の依存関係** ] プロパティに追加します。

メイクを使用してビルドされたプロジェクトの場合、 **/clr** を追加すると、互換性のないコンパイラオプションを手動で無効にする必要があります。 **/Clr** と互換性のないコンパイラオプションについては、「/[/Clr の制限事項](../build/reference/clr-restrictions.md)」を参照してください。

### <a name="precompiled-headers"></a>プリコンパイル済みヘッダー

プリコンパイル済みヘッダーは、 **/clr** でサポートされています。 ただし、一部の CPP ファイルを **/clr** でコンパイルするだけの場合 (ネイティブとして残りをコンパイルする場合)、 **/clr** で生成されたプリコンパイル済みヘッダーは **/clr** を使用して生成されたヘッダーと互換性がないため、一部の変更が必要になります。 この非互換性は、 **/clr** によってメタデータが生成され、メタデータが必要になるためです。 このため、 **/clr** でコンパイルされたモジュールでは、メタデータを含まないプリコンパイル済みヘッダーを使用できません。また、非 **/clr** モジュールでは、メタデータを含むプリコンパイル済みヘッダーファイルを使用できません。

いくつかのモジュールが **/clr** でコンパイルされたプロジェクトをコンパイルする最も簡単な方法は、プリコンパイル済みヘッダーを完全に無効にすることです。 (プロジェクトの [プロパティ ページ] ダイアログで C/C++ ノードを開き、[プリコンパイル済みヘッダー] を選択します。 次に、[プリコンパイル済みヘッダーの作成/使用] プロパティを 「プリコンパイル済みヘッダーを使用しない」 に変更します)。

しかし、特に大きなプロジェクトの場合、プリコンパイル済みヘッダーを使用するとコンパイルの処理速度がかなり短縮されるので、この機能を無効化することはお勧めしません。 この場合は、別のプリコンパイル済みヘッダーを使用するように **/clr** ファイルと非 **/clr** ファイルを構成することをお勧めします。 これを行うには、**ソリューションエクスプローラー** を使用して **/clr** コンパイルするモジュールを複数選択し、グループを右クリックして [プロパティ] を選択します。 次に、[ファイルを使用して PCH を作成/使用] プロパティと [プリコンパイル済みヘッダー ファイル] プロパティの両方を変更し、それぞれ異なるヘッダー ファイル名と PCH ファイルを使用するように設定します。

## <a name="fixing-errors"></a>エラーの修正

**/Clr** を使用してコンパイルすると、コンパイラ、リンカー、またはランタイムエラーが発生する可能性があります。 このセクションでは、最も一般的な問題について説明します。

### <a name="metadata-merge"></a>メタデータのマージ

データ型のバージョンが異なる場合、2 つの型に対して生成されるメタデータが一致しないため、リンカーのエラーが発生することがあります (これは通常、型のメンバーが条件付きで定義されているが、その型を使用するすべての CPP ファイルで条件が同じではない場合に発生します)。この場合、リンカーは失敗し、シンボル名と、型が定義されている2番目の OBJ ファイルの名前のみを報告します。 多くの場合、OBJ ファイルがリンカーに送られる順序を変更し、他のデータ型バージョンの位置がリンカーにわかるようにすると対処できます。

### <a name="loader-lock-deadlock"></a>ローダー ロックのデッドロック

"ローダーロックのデッドロック" は発生する可能性がありますが、決定的であり、実行時に検出および報告されます。 詳細については、「 [混合アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md) 」を参照してください。

### <a name="data-exports"></a>データのエクスポート

DLL データのエクスポートはエラーの原因にもなりやすいため、お勧めしません。 これは、DLL のデータ セクションは、DLL のマネージド部分の一部が実行されるまで初期化されていると保証されないためです。 [#Using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)を使用してメタデータを参照します。

### <a name="type-visibility"></a>型の可視性

ネイティブ型は、既定ではプライベートです。 これで、ネイティブ型は DLL の外側では見えなくなります。 このエラー **`public`** を解決するには、これらの型にを追加します。

### <a name="floating-point-and-alignment-issues"></a>浮動小数点とアラインメントの問題

`__controlfp` は、共通言語ランタイムではサポートされていません (詳細については [、「_control87、_controlfp、 \_ _control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) 」を参照してください)。 また、CLR は [align](../cpp/align-cpp.md)を尊重しません。

### <a name="com-initialization"></a>COM の初期化

共通言語ランタイムは、モジュールが初期化されると自動的に COM を初期化します (自動的に初期化される場合、COM は MTA として初期化されます)。 その結果、明示的に COM を初期化すると、COM が既に初期化されていることを示すリターン コードが生成されます。 COM が CLR によって既にいずれかのスレッド モデルに初期化されている場合、別のスレッド モデルを使用して明示的に COM を初期化しようとすると、アプリケーションが失敗するおそれがあります。

共通言語ランタイムは、既定で COM を MTA として起動します。これを変更するには、 [/CLRTHREADATTRIBUTE (CLR スレッド属性の設定)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) を使用します。

### <a name="performance-issues"></a>パフォーマンスの問題

MSIL に対して生成されたネイティブの C++ メソッドが (仮想関数呼び出し、または関数ポインターの使用によって) 間接的に呼び出されると、パフォーマンスが低下することがあります。 詳細については、「 [ダブルサンキング](../dotnet/double-thunking-cpp.md)」を参照してください。

ネイティブから MSIL に移動すると、ワーキング セットのサイズが増加することがわかります。 これは、共通言語ランタイムが、プログラムを正しく実行するための多くの機能を提供するためです。 **/Clr** アプリケーションが正常に実行されていない場合は、C4793 (既定ではオフ) を有効にすることができます。詳細については、「[コンパイラの警告 (レベル1および 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) 」を参照してください。

### <a name="program-crashes-on-shutdown"></a>シャットダウン時のプログラムの衝突

場合によっては、マネージド コードが実行を終了する前に CLR がシャットダウンすることがあります。 `std::set_terminate` と `SIGTERM` を使用すると、この問題が発生します。 詳細については、「 [Signal 定数](../c-runtime-library/signal-constants.md) 」と「 [set_terminate](../c-runtime-library/abnormal-termination.md) 」を参照してください。

## <a name="using-new-visual-c-features"></a>Visual C++ の新機能の使用

アプリケーションのコンパイル、リンク、および実行が完了すると、 **/clr** でコンパイルされた任意のモジュールで .net 機能を使用できるようになります。 詳細については、「[Component Extensions for Runtime Platforms](../extensions/component-extensions-for-runtime-platforms.md)」を参照してください。

Visual C++ での .NET プログラミングの詳細については、以下の項目を参照してください。

- [C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)

- [ランタイム プラットフォームのコンポーネントの拡張機能](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>関連項目

[混合 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
