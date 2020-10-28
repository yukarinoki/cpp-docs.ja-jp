---
title: /clr (共通言語ランタイムのコンパイル)
description: Microsoft C++ コンパイラオプション/clr を使用して、C++/CLI および C++ コードをマネージコードとしてコンパイルします。
ms.date: 10/27/2020
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
ms.openlocfilehash: 9d27d9fb6226f84c4ea67a8f9387a595ba65468b
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907598"
---
# <a name="clr-common-language-runtime-compilation"></a>`/clr` (共通言語ランタイムのコンパイル)

アプリケーションとコンポーネントが共通言語ランタイム (CLR) の機能を使用して、C++/CLI コンパイルを有効にできるようにします。

## <a name="syntax"></a>構文

> **`/clr`**\[**`:`**_オプション_ ]

## <a name="arguments"></a>引数

*オプション*\
次のコンマ区切りの引数の1つ以上。

- なし

   オプションを使用しない場合、 **`/clr`** コンポーネントのメタデータが作成されます。 このメタデータは、他の CLR アプリケーションで使用でき、コンポーネントが他の CLR コンポーネントのメタデータの型とデータを使用できるようにします。 「[混在 (ネイティブおよびマネージド) アセンブリ](../../dotnet/mixed-native-and-managed-assemblies.md)」を参照してください。

- **`NetCore`**

   **`/clr:NetCore`** 最新のクロスプラットフォーム .NET framework (.NET Core とも呼ばれます) を使用して、コンポーネントのメタデータとコードを作成します。 メタデータは、他の .NET Core アプリケーションで使用できます。 また、オプションを使用すると、コンポーネントは、他の .NET Core コンポーネントのメタデータの型とデータを使用できます。

- **`nostdlib`**

   既定のディレクトリを無視するようにコンパイラに指示し *`\clr`* ます。 System.dll などの DLL の複数のバージョンを含めると、コンパイラはエラーを生成します。 このオプションを使用すると、コンパイル時に使用する特定のフレームワークを指定できます。

- **`pure`**

   **`/clr:pure` は非推奨とさ** れます。 このオプションは、Visual Studio 2017 以降で削除されます。 純粋 MSIL にする必要があるコードは、C# に移植することをお勧めします。

- **`safe`**

   **`/clr:safe` は非推奨とさ** れます。 このオプションは、Visual Studio 2017 以降で削除されます。 安全 MSIL にする必要があるコードは、C# に移植することをお勧めします。

- **`noAssembly`**

   **`/clr:noAssembly` は非推奨とさ** れます。 代わりに[ `/LN` (MSIL モジュールの作成)](ln-create-msil-module.md)を使用してください。

   アセンブリマニフェストを出力ファイルに挿入しないようコンパイラに指示します。 既定では、このオプションは無効になってい **`noAssembly`** ます。

   マニフェストにアセンブリメタデータがないマネージプログラムは、 *モジュール* と呼ばれます。 オプションは、 **`noAssembly`** モジュールを生成するためにのみ使用できます。 およびを使用してコンパイルする場合は、 [`/c`](c-compile-without-linking.md) **`/clr:noAssembly`** [`/NOASSEMBLY`](noassembly-create-a-msil-module.md) リンカーフェーズでオプションを指定してモジュールを作成します。

   Visual Studio 2005 より前 **`/clr:noAssembly`** 。が必要 **`/LD`** です。 **`/LD`** を指定すると、が暗黙的に使用されるようになり **`/clr:noAssembly`** ます。

- **`initialAppDomain`**

   **`initialAppDomain` は互換性のために残さ** れています。 C++/CLI アプリケーションを CLR の version 1 で実行できるようにします。  を使用するアプリケーションは **`initialAppDomain`** 、CLR のバージョン1ではサポートされていないため、ASP.NET を使用するアプリケーションでは使用できません。

## <a name="remarks"></a>解説

*マネージコード* は、CLR によって検査および管理できるコードです。 マネージド コードはマネージド オブジェクトにアクセスできます。 詳細については、「 [ `/clr` 制限](clr-restrictions.md)」を参照してください。

C++ でマネージ型を定義および使用するアプリケーションを開発する方法については、「 [ランタイムプラットフォームのコンポーネント拡張](../../extensions/component-extensions-for-runtime-platforms.md)」を参照してください。

を使用してコンパイルされたアプリケーションは、 **`/clr`** マネージデータを含むことができます。

マネージアプリケーションでのデバッグを有効にするには、「 [ `/ASSEMBLYDEBUG` (DebuggableAttribute の追加)](assemblydebug-add-debuggableattribute.md)」を参照してください。

CLR 型のみがガベージコレクションヒープでインスタンス化されます。 詳細については、「[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。 関数をネイティブ コードにコンパイルするには、 `unmanaged` プラグマを使用します。 詳細については、「」 [ `managed` を `unmanaged` ](../../preprocessor/managed-unmanaged.md)参照してください。

既定では、は **`/clr`** 無効です。 **`/clr`** が有効な場合は、 **`/MD`** も有効になります。 詳細については、「」、「」 [ `/MD` `/MT` `/LD` (Run-Time ライブラリの使用)](md-mt-ld-use-run-time-library.md)を参照してください。 **`/MD`** 動的にリンクされたマルチスレッドバージョンのランタイムルーチンが標準ヘッダーファイルから選択されていることを確認します。 マネージド プログラミングでマルチスレッドが必要なのは、CLR のガベージ コレクターが、補助スレッドでファイナライザーを実行するためです。

を使用してコンパイルする場合は、リンカーオプションを使用して、結果として生成される **`/c`** 出力ファイルの CLR 型を指定でき [`/CLRIMAGETYPE`](clrimagetype-specify-type-of-clr-image.md) ます。

**`/clr`** は **`/EHa`** を意味し、では他の **`/EH`** オプションはサポートされていません **`/clr`** 。 詳細については、「 [ `/EH` (例外処理モデル)](eh-exception-handling-model.md)」を参照してください。

ファイルの CLR イメージの種類を確認する方法の詳細については、「」を参照してください [`/CLRHEADER`](clrheader.md) 。

リンカーの特定の呼び出しに渡されるすべてのモジュールは、同じランタイムライブラリコンパイラオプション (または) を使用してコンパイルする必要があり **`/MD`** **`/LD`** ます。

リンカーオプションを使用して、 [`/ASSEMBLYRESOURCE`](assemblyresource-embed-a-managed-resource.md) リソースをアセンブリに埋め込みます。 [`/DELAYSIGN`](delaysign-partially-sign-an-assembly.md)、 [`/KEYCONTAINER`](keycontainer-specify-a-key-container-to-sign-an-assembly.md) 、および [`/KEYFILE`](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) リンカーオプションでは、アセンブリの作成方法をカスタマイズすることもできます。

**`/clr`** を使用する場合、 `_MANAGED` シンボルは1に定義されます。 詳細については、「 [定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。

ネイティブオブジェクトファイル内のグローバル変数は、( `DllMain` 実行可能ファイルが DLL である場合は) 最初に初期化され、その後、マネージセクションのグローバル変数が (マネージコードが実行される前に) 初期化されます。 [`#pragma init_seg`](../../preprocessor/init-seg.md) は、マネージカテゴリおよびアンマネージカテゴリの初期化の順序にのみ影響します。

### <a name="metadata-and-unnamed-classes"></a>メタデータと名前のないクラス

名前のないクラスは、などの名前のメタデータに表示され  `$UnnamedClass$<crc-of-current-file-name>$<index>$` `<index>` ます。は、コンパイル時に名前のないクラスの順次カウントです。 次のコードの例では、名前のないクラスをメタデータに生成します。

```cpp
// clr_unnamed_class.cpp
// compile by using: /clr /LD
class {} x;
```

メタデータを表示するには、ildasm.exe を使用します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンを [ **すべての構成** ] に設定し、[ **プラットフォーム** ] ドロップダウンを [ **すべてのプラットフォーム** ] に設定します。

1. [ **構成プロパティ** ] [  >  **C/c + +**  >  **全般** ] ページを選択します。

1. **共通言語ランタイムサポート** プロパティを変更します。 **[OK]** を選択して変更を保存します。

> [!NOTE]
> Visual Studio IDE では、[ **`/clr`** **Configuration Properties**  >  プロパティページ] ダイアログボックスの [構成プロパティ] [ **C/c + +**  >  **全般** ] ページで、コンパイラオプションを個別に設定できます。 ただし、プロジェクトを作成するには CLR テンプレートを使用することをお勧めします。 CLR コンポーネントを正常に作成するために必要なすべてのプロパティを設定します。 これらのプロパティを設定するもう1つの方法は、[プロパティページ] ダイアログボックスの [ **構成プロパティ** ] の [詳細設定] ページで、[ **共通言語ランタイムサポート** ] プロパティを使用することです  >  **Advanced** 。 このプロパティは、その他のすべての CLR 関連ツールオプションを一度に設定します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md)\
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
