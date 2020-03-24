---
title: '方法: コンパイル時にリソースを含める (C++)'
ms.date: 02/14/2019
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
- vc.editors.resourceincludes
helpviewer_keywords:
- comments [C++], compiled files
- resources [C++], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
- Resource Includes dialog box [C++]
- rc files [C++], changing storage
- symbol header files [C++], changing
- .rc files [C++], changing storage
- symbol header files [C++], read-only
- symbols [C++], symbol header files
- directories [C++], specifying include paths for resources
- include files [C++], specifying for resources
- resources [C++], including in projects
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
ms.openlocfilehash: e931a0246340e81049df6ed0f8e26a4b91b570c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215194"
---
# <a name="how-to-include-resources-at-compile-time-c"></a>方法: コンパイル時にリソースを含める (C++)

既定では、すべてのリソースは1つのリソーススクリプト (.rc) ファイルに配置されますが、メインの .rc ファイル以外のファイルにリソースを配置する理由は多数あります。

- .Rc ファイルを保存するときに削除されないリソースステートメントにコメントを追加します。

- 既に開発およびテストされ、さらに変更を必要としないリソースを含める。 インクルードされていても .rc 拡張子のないファイルは、リソースエディターで編集することはできません。

- 異なるプロジェクトによって使用されているリソース、またはソースコードのバージョン管理システムの一部であるリソースを含める場合は。 これらのリソースは、変更がすべてのプロジェクトに影響を与える中央の場所に存在する必要があります。

- カスタム形式のリソース (RCDATA リソースなど) を含める場合は。 RCDATA リソースには、`nameID` フィールドの値として式を使用できない特別な要件があります。

これらの条件のいずれかを満たす既存の .rc ファイルにセクションがある場合は、これらのセクションを1つ以上の個別の .rc ファイルに配置し、 **[リソースインクルード]** ダイアログボックスを使用してプロジェクトに追加します。

## <a name="resource-includes"></a>リソースインクルード

コンパイル時に他のファイルのリソースをプロジェクトに追加するには、 **[リソースインクルード]** ダイアログボックスの **[コンパイル時]** に使用するディレクティブ ボックスにリソースを一覧表示します。 **[リソースのインクルード]** ダイアログボックスを使用すると、プロジェクトの .rc ファイルおよびすべての[シンボル](../windows/symbols-resource-identifiers.md)を `Resource.h`内のすべてのリソースを格納するための、プロジェクト環境の通常の作業配置を変更できます。

開始するには、 **[リソースのインクルード]** ダイアログボックスを開きます。[リソースビュー](how-to-create-a-resource-script-file.md#create-resources)で .rc ファイルを右クリックし、 **[リソースインクルード]** を選択して、次のプロパティを確認します。

| プロパティ | 説明 |
|---|---|
| **シンボルヘッダーファイル** | リソースファイルのシンボル定義を格納するヘッダーファイルの名前を変更できます。<br/><br/>詳細については、「[シンボルヘッダーファイルの名前の変更](../windows/changing-the-names-of-symbol-header-files.md)」を参照してください。 |
| **読み取り専用のシンボルディレクティブ** | 変更しないシンボルを含むヘッダーファイルを含めることができます。<br/><br/>たとえば、他のプロジェクトと共有するシンボルファイルなどです。 これには、MFC .h ファイルを含めることもできます。 詳細については、「[共有 (読み取り専用)」または「計算されるシンボルのインクルード](../windows/including-shared-read-only-or-calculated-symbols.md)」を参照してください。 |
| **コンパイル時のディレクティブ** | では、メインリソースファイル内のリソースとは別に作成および編集されるリソースファイルを含めることができます。また、コンパイル時のディレクティブ (条件に応じてリソースを含めるディレクティブなど) を含めたり、カスタム形式のリソースを含めたりすることができます。<br/><br/>また、[コンパイル時に使用する**ディレクティブ] ボックス**を使用して、標準の MFC リソースファイルを含めることもできます。 |

> [!NOTE]
> これらのテキストボックス内のエントリは、それぞれ `TEXTINCLUDE 1`、`TEXTINCLUDE 2`、および `TEXTINCLUDE 3` でマークされた .rc ファイルに表示されます。 詳細については、「[テクニカルノート 35: 複数のリソースファイルとヘッダーファイルC++の使用](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)」を参照してください。

**[リソースインクルード]** ダイアログボックスを使用してリソースファイルに変更を加えた後、変更を有効にするために .rc ファイルを閉じてから再度開く必要があります *。*

### <a name="to-include-resources-in-your-project-at-compile-time"></a>コンパイル時にリソースをインクルードするには

1. 一意のファイル名を持つリソース スクリプト ファイルにリソースを配置します。 *Projectname. .rc*を使用しないでください。これは、メインのリソーススクリプトファイルで使用されるファイルの名前であるためです。

1. [リソースビュー](how-to-create-a-resource-script-file.md#create-resources)で *.rc*ファイルを右クリックし、 **[リソースのインクルード]** を選択します。

1. **[コンパイル時のディレクティブ]** ボックスで、 [#include](../preprocessor/hash-include-directive-c-cpp.md)コンパイラディレクティブを追加して、開発環境のメインリソースファイルに新しいリソースファイルを含めます。

この方法でインクルードされたファイル内のリソースは、コンパイル時にのみ実行可能ファイルの一部になります。プロジェクトのメイン .rc ファイルを操作しているときに編集や変更を行うことはできません。 インクルードされた .rc ファイルを個別に開く必要があります。 .rc 拡張子のないファイルは、リソースエディターで編集することはできません。

### <a name="to-specify-include-directories-for-a-specific-resource-rc-file"></a>特定のリソース (.rc) ファイルのインクルードディレクトリを指定するには

1. **ソリューションエクスプローラー**で *.rc*ファイルを右クリックし、 **[プロパティ]** を選択します。

1. 左ペインで **[リソース]** ノードを選択し、追加のインクルード **[ディレクトリ]** プロパティに追加のインクルードディレクトリを指定します。

### <a name="to-find-symbols-in-resources"></a>リソース内のシンボルを検索するには

1. **メニューに**アクセスして [シンボルの検索] > [検索](/visualstudio/ide/go-to)します。

   > [!TIP]
   > 検索で[正規表現](/visualstudio/ide/using-regular-expressions-in-visual-studio)を使用するには、 **[シンボル]** の検索 ではなく **[編集]** メニューの [フォルダーを選択して[検索](/visualstudio/ide/reference/find-command)] を選択します。 [[検索] ダイアログボックス](/visualstudio/ide/finding-and-replacing-text)の **[使用: 正規表現]** チェックボックスをオンにし、 **[検索する文字列]** ボックスで、ドロップダウンリストから標準の検索式を選択します。 この一覧から式を選択すると、[検索する文字列] ボックスの検索テキストとして置き換え**ら**れます。

1. [**検索**する文字列] ボックスで、ドロップダウンリストから以前の検索文字列を選択するか、検索するアクセラレータキー (`ID_ACCEL1`など) を入力します。

1. **[検索]** オプションのいずれかを選択し、 **[次を検索]** を選択します。

> [!NOTE]
> 文字列リソース、アクセラレータ リソース、またはバイナリ リソース内のシンボルは検索できません。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>参照

[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[方法: リソースを作成する](../windows/how-to-create-a-resource-script-file.md)<br/>
[方法: リソースを管理する](../windows/how-to-copy-resources.md)<br/>
