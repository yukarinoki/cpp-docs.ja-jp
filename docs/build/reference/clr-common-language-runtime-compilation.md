---
title: -clr (共通言語ランタイムのコンパイル) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b46f61ef727c1b283137bb3d537d2dbad416c1d8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703821"
---
# <a name="clr-common-language-runtime-compilation"></a>/clr (共通言語ランタイムのコンパイル)

アプリケーションおよびコンポーネントで、共通言語ランタイム (CLR) の機能を使用できるようにします。

## <a name="syntax"></a>構文

> **/clr**[**:**_オプション_]

## <a name="arguments"></a>引数

*options*<br/>
次の 1 つまたは複数のスイッチをコンマで区切って指定します。

- none

   オプションなしで **/clr**アプリケーションのメタデータを作成します。 このメタデータは、他の CLR アプリケーションで使用できます。また、このメタデータによって、他の CLR コンポーネントのメタデータの型とデータをアプリケーションで使用できるようになります。 詳細については、次を参照してください。[混在 (ネイティブおよびマネージ) アセンブリ](../../dotnet/mixed-native-and-managed-assemblies.md)と[方法:/clr:pure に移行](../../dotnet/how-to-migrate-to-clr.md)します。

- **純粋です**

   **/clr:/clr:pure は非推奨**します。 コンパイラの将来のバージョンでこのオプションがサポートされない可能性があります。 純粋 MSIL にする必要があるコードは、C# に移植することをお勧めします。

- **safe**

   **/clr:safe は非推奨**します。 コンパイラの将来のバージョンでこのオプションがサポートされない可能性があります。 C# に安全な MSIL にする必要があるコードを移植することをお勧めします。

- **noAssembly**

   **/clr:noAssembly は非推奨**します。 代わりに、 [/LN (Create MSIL Module)](../../build/reference/ln-create-msil-module.md) を使用してください。

   アセンブリ マニフェストを出力ファイルに挿入できないことを指定します。 既定では、 **noAssembly** オプションはオフです。

   マニフェストにアセンブリ メタデータがないマネージド プログラムを、 *モジュール*と呼びます。 **noAssembly** オプションは、モジュールを生成するときのみ使用できます。 [/c](../../build/reference/c-compile-without-linking.md) と **/clr:noAssembly**を使用してコンパイルする場合は、リンカーのフェーズで [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) オプションを指定してモジュールを作成します。

   Visual C++ 2005 より前のバージョンでは、 **/clr:noAssembly** には **/LD**が必要です。 現在は、**/LD** を指定すると **/LD**が暗黙的に指定されるようになっています。

- **initialAppDomain**

   CLR のバージョン 1 で実行する Visual C アプリケーションを有効にします。  CLR の Version 1 では ASP.NET をサポートしていないため、 **initialAppDomain** を使用してコンパイルされたアプリケーションは、ASP.NET を使用しているアプリケーションでは使用しないでください。

- **nostdlib**

   既定の \clr ディレクトリを無視するようにコンパイラに指示します。 System.dll などの DLL の複数のバージョンを含めると、コンパイラはエラーを生成します。 このオプションを使用すると、コンパイル時に使用する特定のフレームワークを指定できます。

## <a name="remarks"></a>Remarks

マネージド コードは、CLR によって検査および管理できるコードです。 マネージド コードはマネージド オブジェクトにアクセスできます。 詳細については、「 [/clr Restrictions](../../build/reference/clr-restrictions.md)」を参照してください。

マネージド型を定義および使用するアプリケーションの開発方法については、「 [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md)。

**/clr** を使用してコンパイルされたアプリケーションには、マネージド データがある場合とない場合があります。

マネージ アプリケーションでのデバッグを有効にするのを参照してください。 [/ASSEMBLYDEBUG (DebuggableAttribute の追加)](../../build/reference/assemblydebug-add-debuggableattribute.md)します。

ガベージ コレクトされたヒープでインスタンス化されるのは CLR 型のみです。 詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)します。 関数をネイティブ コードにコンパイルするには、 `unmanaged` プラグマを使用します。 詳細については、次を参照してください。[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)します。

既定では、 **/clr** は無効です。 **/clr** が有効な場合は **/MD** も有効です。 詳細については、「[/MD、/MT、/LD (ランタイム ライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。 **/MD** を使用すると、動的にリンクされるマルチスレッド バージョンのランタイム ルーチンが標準ヘッダー (.h) ファイルから選択されるようになります。 マネージド プログラミングでマルチスレッドが必要なのは、CLR のガベージ コレクターが、補助スレッドでファイナライザーを実行するためです。

使用してコンパイルする場合 **/c**、結果として出力ファイルの CLR 型を指定する[/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)します。

**/clr** は **/EHa**を暗黙的に指定するため、 **/clr** では他の **/EH**オプションを指定できません。 詳細については、「[/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)」を参照してください。

ファイルの CLR イメージのタイプを判断する方法については、「 [/CLRHEADER](../../build/reference/clrheader.md)」を参照してください。

リンカーの特定の呼び出しに渡されるすべてのモジュールは、同じランタイム ライブラリ コンパイラ オプション (**/MD** または **/LD**) を使用してコンパイルされている必要があります。

[/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) リンカー オプションを使用して、アセンブリにリソースを埋め込みます。 [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)、 [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)、および [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) の各リンカー オプションでも、アセンブリの作成方法をカスタマイズできます。

**/clr** が使用されるときは、 `_MANAGED` シンボルは 1 に定義されます。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。

最初にネイティブなオブジェクト ファイルのグローバル変数が (実行可能ファイルが DLL の場合は DllMain の実行中に) 初期化され、その後でマネージド セクションのグローバル変数が (いずれかのマネージド コードが実行される前に) 初期化されます。 `#pragma` [init_seg](../../preprocessor/init-seg.md)マネージおよびアンマネージ カテゴリ内の初期化の順序にのみ影響します。

## <a name="metadata-and-unnamed-classes"></a>メタデータと名前のないクラス

名前のないクラスは、メタデータに `$UnnamedClass$`*crc-of-current-file-name*`$`*index*`$`のような名前で表示されます。この *index* は、コンパイル時に名前のないクラスに与えられる連続番号です。 次のコードの例では、名前のないクラスをメタデータに生成します。

```cpp
// clr_unnamed_class.cpp
// compile by using: /clr /LD
class {} x;
```

メタデータを表示するには、ildasm.exe を使用します。

## <a name="managed-extensions-for-c"></a>C++ マネージド拡張

Visual C++ では、 **/clr:oldsyntax** オプションがサポートされなくなっています。 このオプションは Visual Studio 2005 で非推奨とされました。 C++ でのマネージド コードの記述でサポートされている構文は、C++/CLI です。 詳細については、「 [Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md)」を参照してください。

C++ のマネージド拡張を使用するコードを使用している場合は、移植して C++/CLI 構文を使用することをお勧めします。 コードの移植方法の詳細については、「 [C++/CLI Migration Primer](../../dotnet/cpp-cli-migration-primer.md)」を参照してください。

#### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. **ソリューション エクスプローラー**でプロジェクト名を右クリックし、 **[プロパティ]** をクリックして、プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。

1. 選択、**構成プロパティ** > **全般**プロパティ ページ。

1. 変更、**共通言語ランタイム サポート**プロパティ。

   > [!NOTE]
   > **/clr** が **[プロパティ ページ]** ダイアログ ボックスで有効になっている場合は、 **/clr** と互換性のないコンパイラ オプション プロパティも必要に応じて調整されます。 たとえば、 **/RTC** が設定された後で **/clr** が有効になった場合、 **/RTC** はオフになります。
   >
   >  また、 **/clr** アプリケーションをデバッグする場合、 **[デバッガーの種類]** プロパティを **[混合]** または **[マネージドのみ]** に設定します。 詳細については、次を参照してください。 [C++ デバッグ構成のプロジェクト設定](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)します。

   方法については、モジュールの作成を参照してください[/NOASSEMBLY (MSIL モジュールの作成)](../../build/reference/noassembly-create-a-msil-module.md)します。

#### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)