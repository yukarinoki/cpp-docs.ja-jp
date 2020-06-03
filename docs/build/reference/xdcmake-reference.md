---
title: XDCMake リファレンス
ms.date: 11/04/2016
f1_keywords:
- xdcmake
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
ms.openlocfilehash: 9970470d1feb471f9e0b8c9284a08337dac7ef0f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335855"
---
# <a name="xdcmake-reference"></a>XDCMake リファレンス

xdcmake.exe は .xdc ファイルを .xml ファイルにコンパイルするプログラムです。 ソース コードが[/doc](doc-process-documentation-comments-c-cpp.md)でコンパイルされ、ソース コード ファイルに XML タグでマークアップされたドキュメント コメントが含まれている場合、各ソース コード ファイルの MSVC コンパイラによって .xdc ファイルが作成されます。

### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で xdcmake.exe を使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]** フォルダーを開きます。

1. **[XML Document Comments]\(XML ドキュメント コメント\)** プロパティ ページをクリックします。

> [!NOTE]
> コマンド ラインの xdcmake.exe オプションは、xdcmake.exe が開発環境 (プロパティ ページ) で使用されるときのオプションとは異なります。 開発環境で xdcmake.exe を使用する方法については、「[[XML ドキュメント ジェネレーター] プロパティ ページ](xml-document-generator-tool-property-pages.md)」を参照してください。

## <a name="syntax"></a>構文

xdcmake `input_filename options`

## <a name="parameters"></a>パラメーター

*input_filename*<br/>
xdcmake.exe への入力として使用されている .xdc ファイルのファイル名。 1 つまたは複数の .xdc ファイルを指定するか、*.xdc と指定し、現在のディレクトリにあるすべての .xdc ファイルを使用します。

*オプション*<br/>
次をいくつか指定できます。指定しないこともできます。

|オプション|説明|
|------------|-----------------|
|/?, /help|xdcmake.exe のヘルプを表示します。|
|/assembly:*filename*|.xml ファイルに \<assembly> タグの値を指定できます。  既定では、\<assembly> タグは .xml ファイルのファイル名と同じになります。|
|/nologo|著作権メッセージを表示しません。|
|/out:*filename*|.xml ファイルの名前を指定できます。  既定では、.xml ファイルの名前は xdcmake.exe によって処理される最初の .xdc ファイルのファイル名になります。|

## <a name="remarks"></a>解説

Visual Studio は、プロジェクトのビルド時、xdcmake.exe を自動的に呼び出します。 コマンド ラインで xdcmake.exe を呼び出すこともできます。

ドキュメントのコメントをソース コード ファイルに追加する詳細については、[ドキュメント コメントとして推奨されるタグ](recommended-tags-for-documentation-comments-visual-cpp.md)に関するページを参照してください。

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
