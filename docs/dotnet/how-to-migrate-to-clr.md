---
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
ms.openlocfilehash: 339b1f3172d8b82ece3e98f117f53ed399cbd4e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376077"
---
# <a name="how-to-migrate-to-clr"></a>方法: /clr に移行する

このトピックでは **、/clr**を使用してネイティブ コードをコンパイルするときに発生する問題について説明します (詳細については[、「/clr (共通言語ランタイムのコンパイル)」を](../build/reference/clr-common-language-runtime-compilation.md)参照してください)。 **/clr**を使用すると、ネイティブ C++ コードを呼び出し、他のネイティブ C++ コードに加えて .NET アセンブリから呼び出すことができます。 **/clr**を使用してコンパイルする利点の詳細については、「[混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)」および「[ネイティブおよび .NET](../dotnet/native-and-dotnet-interoperability.md)の相互運用性」を参照してください。

## <a name="known-issues-compiling-library-projects-with-clr"></a>/clr でライブラリ プロジェクトをコンパイルする場合の既知の問題

**/clr**を使用してライブラリ プロジェクトをコンパイルする場合、Visual Studio にはいくつかの既知の問題が含まれています。

- コードは[、実行時に CRuntimeClass::FromName](../mfc/reference/cruntimeclass-structure.md#fromname)を使用して型を照会できます。 ただし、型が MSIL .dll **(/clr**でコンパイルされた) にある場合`FromName`、マネージ .dll で静的コンストラクターが実行される前に呼び出しが失敗することがあります (コードがマネージ .dll で実行された後に FromName 呼び出しが発生した場合、この問題は発生しません)。 この問題を回避するには、マネージド静的コンストラクターを強制的に構築します。それには、マネージド .dll で関数を定義してエクスポートし、その関数をネイティブ MFC アプリケーションから呼び出します。 次に例を示します。

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>Visual C++ でのコンパイル

プロジェクト内の任意のモジュールで **/clr**を使用する前に、まずコンパイルし、Visual Studio 2010 でネイティブ プロジェクトをリンクします。

次の手順は、次の順序で **、/clr**コンパイルへの最も簡単なパスを提供します。 これらの手順では、手順ごとにプロジェクトをコンパイルして実行することが重要です。

### <a name="versions-prior-to-visual-studio-2003"></a>バージョンが Visual Studio 2003 より前のバージョン

Visual Studio 2003 より前のバージョンから Visual Studio 2010 にアップグレードする場合は、Visual Studio 2003 で拡張された C++ 標準準拠に関連するコンパイラ エラーが表示される場合があります。

### <a name="upgrading-from-visual-studio-2003"></a>Visual Studio 2003 からのアップグレード

Visual Studio 2003 で以前にビルドされたプロジェクトも、最初に **/clr**なしでコンパイルする必要があります。 最も注意が必要になる可能性のある変更は、 [CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)です。 CRT を使用するコードでは、廃止警告が生成される可能性があります。 これらの警告は抑制できますが、セキュリティ[が強化された新しいバージョンの CRT 関数](../c-runtime-library/security-enhanced-versions-of-crt-functions.md)への移行が推奨されます。

### <a name="upgrading-from-managed-extensions-for-c"></a>C++ マネージド拡張からのアップグレード

Visual Studio 2005 以降、C++ マネージ拡張で記述されたコードは **/clr**の下でコンパイルされません。

## <a name="convert-c-code-to-c"></a>C コードから C++ への変換

Visual Studio は C ファイルをコンパイルしますが **、/clr**コンパイルのために C++ に変換する必要があります。 実際のファイル名は変更する必要はありません。**/Tp**を使用できます[(/Tc、/Tp、/TC、/TP (ソース ファイルの種類を指定する)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md)を参照してください。C++ のソース コード ファイルは **/clr**に必要ですが、オブジェクト指向のパラダイムを使用するようにコードを再考慮する必要はありません。

C コードは、C++ ファイルとしてコンパイルするときは変更を必要とする可能性があります。 C++ の型保証の規則は厳密なので、型の変換はキャストで明示的に行う必要があります。 たとえば、malloc は void ポインターを返しますが、キャストによる C では任意の型のポインターに割り当てることができます。

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

また C++ では関数ポインターの型も厳密に保証されているので、次のような C コードは変更が必要です。 C++ では、関数ポインターの型を定義する `typedef` を作成し、その後その型を使用して関数ポインターをキャストすることをお勧めします。

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

また C++ では、関数を参照したり呼び出すには、その前にプロトタイプを作成するか完全に定義する必要があります。

C++ のキーワードとして使用される C コードで使用される識別子 (**仮想**、**新規**、**削除**、 **bool**、 **true**、 **false**など ) の名前を変更する必要があります。 これは一般的に、単純な検索置換操作だけで行うことができます。

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>プロジェクト設定の再構成

プロジェクトが Visual Studio 2010 でコンパイルおよび実行された後は、既定の構成を変更するのではなく **、/clr**用の新しいプロジェクト構成を作成する必要があります。 **/clr**は一部のコンパイラ オプションと互換性がなく、個別の構成を作成すると、プロジェクトをネイティブまたはマネージとしてビルドできます。 プロパティ ページ ダイアログ ボックスで **/clr**を選択すると **、/clr**と互換性のないプロジェクト設定が無効になります **(/clr**が選択されていない場合は、無効なオプションは自動的に復元されません)。

### <a name="create-new-project-configurations"></a>新しいプロジェクト構成の作成

[**新しいプロジェクト構成] ダイアログ ボックス**(**Build** > **ビルド構成マネージャー** > **のアクティブ ソリューション構成** > **New**) の [**設定のコピー元**] オプションを使用して、既存のプロジェクト設定に基づいてプロジェクト構成を作成できます。 これを、デバッグ構成に対して 1 回、リリース構成に対して 1 回実行してください。 その後の変更は **、/clr**固有の構成にのみ適用でき、元のプロジェクト構成はそのまま残ります。

カスタム ビルド規則を使用するプロジェクトには、特別な注意が必要な場合があります。

この手順は、メイクファイルを使用するプロジェクトにとって別の意味があります。 この場合、別のビルド ターゲットを構成するか **、/clr**コンパイルに固有のバージョンを元のコピーから作成できます。

### <a name="change-project-settings"></a>プロジェクトの設定の変更

**開発環境で /clr**を選択する場合は[、「/clr (共通言語ランタイムのコンパイル)」](../build/reference/clr-common-language-runtime-compilation.md)の手順に従います。 既に説明したように、この手順によって競合するプロジェクト設定は自動的に無効になります。

> [!NOTE]
> マネージ ライブラリまたは Web サービス プロジェクトを Visual Studio 2003 からアップグレードする場合 **、/Zl**コンパイラ オプションが **[コマンド ライン**] プロパティ ページに追加されます。 これによって LNK2001 が発生します。 解決するには、**コマンド ライン**プロパティ ページから **/Zl**を削除します。 詳細については[、/Zl (既定のライブラリ名を省略する)](../build/reference/zl-omit-default-library-name.md)および[コンパイラとビルド プロパティの設定](../build/working-with-project-properties.md)を参照してください。 または、リンカーの**追加依存関係**プロパティに msvcrt.lib と msvcmrt.lib を追加します。

メイクファイルを使用してビルドされたプロジェクトでは **、/clr**が追加されると、互換性のないコンパイラ オプションを手動で無効にする必要があります。 /clr と互換性のないコンパイラ オプションの詳細については、 / **/clr**[の制限](../build/reference/clr-restrictions.md)を参照してください。

### <a name="precompiled-headers"></a>プリコンパイル済みヘッダー

プリコンパイル済みヘッダーは **/clr**でサポートされています。 ただし **、/clr**を使用して CPP ファイルの一部だけをコンパイルする場合 (残りの部分をネイティブとしてコンパイルする **)、/clr**で生成されたプリコンパイル済みヘッダーは **/clr**なしで生成されたものと互換性がないため、いくつかの変更が必要になります。 この非互換性は **、/clr**がメタデータを生成し、必要とするという事実によるものです。 したがって **、コンパイルされた /clr**のモジュールは、メタデータを含まないプリコンパイル済みヘッダーを使用できず **、/clr**以外のモジュールは、メタ データを含むプリコンパイル済みヘッダー ファイルを使用できません。

一部のモジュールがコンパイルされているプロジェクトをコンパイルする最も簡単な方法 **/clr**は、プリコンパイル済みヘッダーを完全に無効にすることです。 (プロジェクトの [プロパティ ページ] ダイアログで C/C++ ノードを開き、[プリコンパイル済みヘッダー] を選択します。 次に、[プリコンパイル済みヘッダーの作成/使用] プロパティを 「プリコンパイル済みヘッダーを使用しない」 に変更します)。

しかし、特に大きなプロジェクトの場合、プリコンパイル済みヘッダーを使用するとコンパイルの処理速度がかなり短縮されるので、この機能を無効化することはお勧めしません。 この場合 **、/clr**ファイルと**非 /clr**ファイルを構成して、個別のプリコンパイル済みヘッダーを使用することをお勧めします。 これは、**ソリューション エクスプローラー**を使用して **/clr**をコンパイルするモジュールを複数選択し、グループを右クリックして [プロパティ] を選択することで、1 つの手順で実行できます。 次に、[ファイルを使用して PCH を作成/使用] プロパティと [プリコンパイル済みヘッダー ファイル] プロパティの両方を変更し、それぞれ異なるヘッダー ファイル名と PCH ファイルを使用するように設定します。

## <a name="fixing-errors"></a>エラーの修正

**/clr**を指定してコンパイルすると、コンパイラ、リンカー、またはランタイムエラーが発生する可能性があります。 このセクションでは、最も一般的な問題について説明します。

### <a name="metadata-merge"></a>メタデータのマージ

データ型のバージョンが異なる場合、2 つの型に対して生成されるメタデータが一致しないため、リンカーのエラーが発生することがあります (これは通常、型のメンバーが条件付きで定義されているが、その型を使用するすべての CPP ファイルで条件が同じではない場合に発生します。この場合、リンカーは、シンボル名と、型が定義された 2 番目の OBJ ファイルの名前のみを報告して失敗します。 多くの場合、OBJ ファイルがリンカーに送られる順序を変更し、他のデータ型バージョンの位置がリンカーにわかるようにすると対処できます。

### <a name="loader-lock-deadlock"></a>ローダー ロックのデッドロック

"ローダー ロックのデッドロック" は発生する可能性がありますが、確定的なものであり、実行時に検出および報告されます。 詳細な背景、ガイダンス、およびソリューションについては、「[混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)」を参照してください。

### <a name="data-exports"></a>データのエクスポート

DLL データのエクスポートはエラーの原因にもなりやすいため、お勧めしません。 これは、DLL のデータ セクションは、DLL のマネージド部分の一部が実行されるまで初期化されていると保証されないためです。 [#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)を使用してメタデータを参照します。

### <a name="type-visibility"></a>型の可視性

ネイティブ型は、既定ではプライベートです。 これで、ネイティブ型は DLL の外側では見えなくなります。 このエラーを解決するには、これらの型に `public` を追加します。

### <a name="floating-point-and-alignment-issues"></a>浮動小数点とアラインメントの問題

`__controlfp`は共通言語ランタイムではサポートされていません (詳細については[、「_control87、_controlfp、_control87_2」\_](../c-runtime-library/reference/control87-controlfp-control87-2.md)を参照してください)。 CLR は、[整列](../cpp/align-cpp.md)を考慮しません。

### <a name="com-initialization"></a>COM の初期化

共通言語ランタイムは、モジュールが初期化されると自動的に COM を初期化します (自動的に初期化される場合、COM は MTA として初期化されます)。 その結果、明示的に COM を初期化すると、COM が既に初期化されていることを示すリターン コードが生成されます。 COM が CLR によって既にいずれかのスレッド モデルに初期化されている場合、別のスレッド モデルを使用して明示的に COM を初期化しようとすると、アプリケーションが失敗するおそれがあります。

共通言語ランタイムは、既定で COM を MTA として起動します。これを変更するには[、/CLRTHREADATTRIBUTE (CLR スレッド属性の設定) を](../build/reference/clrthreadattribute-set-clr-thread-attribute.md)使用します。

### <a name="performance-issues"></a>パフォーマンスの問題

MSIL に対して生成されたネイティブの C++ メソッドが (仮想関数呼び出し、または関数ポインターの使用によって) 間接的に呼び出されると、パフォーマンスが低下することがあります。 詳細については、「[ダブル サンキング](../dotnet/double-thunking-cpp.md)」を参照してください。

ネイティブから MSIL に移動すると、ワーキング セットのサイズが増加することがわかります。 これは、共通言語ランタイムが、プログラムを正しく実行するための多くの機能を提供するためです。 **/clr**アプリケーションが正しく実行されていない場合は、C4793 (既定ではオフ) を有効にする必要があります。.、[詳細については、コンパイラの警告 (レベル 1 および 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md)を参照してください。

### <a name="program-crashes-on-shutdown"></a>シャットダウン時のプログラムの衝突

場合によっては、マネージド コードが実行を終了する前に CLR がシャットダウンすることがあります。 `std::set_terminate` と `SIGTERM` を使用すると、この問題が発生します。 詳細については[、シグナル定数](../c-runtime-library/signal-constants.md)と[set_terminate](../c-runtime-library/abnormal-termination.md)を参照してください。

## <a name="using-new-visual-c-features"></a>Visual C++ の新機能の使用

アプリケーションのコンパイル、リンク、および実行後は **、/clr**でコンパイルされた任意のモジュールで .NET 機能を使用できます。 詳細については、「[Component Extensions for Runtime Platforms](../extensions/component-extensions-for-runtime-platforms.md)」を参照してください。

Visual C++ での .NET プログラミングの詳細については、以下の項目を参照してください。

- [C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)

- [ランタイム プラットフォームのコンポーネントの拡張機能](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>関連項目

[混在 (ネイティブおよびマネージド) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)
