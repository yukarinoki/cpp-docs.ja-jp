---
title: インポート ライブラリとエクスポート ファイルのビルド
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
helpviewer_keywords:
- OUT library manager option
- INCLUDE library manager option
- /DEF library manager option
- exporting data
- import libraries, building
- -INCLUDE library manager option
- /OUT library manager option
- DEF library manager option
- -DEF library manager option
- -OUT library manager option
- /INCLUDE library manager option
- -EXPORT library manager option
- exporting data, export (.exp) files
- /EXPORT library manager option
- EXPORT library manager option
- .lib files
- EXP files
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
ms.openlocfilehash: 5cb5224b3edaf84dbcb7c0429044a647fb5ac19a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229754"
---
# <a name="building-an-import-library-and-export-file"></a>インポート ライブラリとエクスポート ファイルのビルド

インポートライブラリとエクスポートファイルをビルドするには、次の構文を使用します。

> **LIB/def**[**:**<em>deffile</em>] [*オプション*] [*objfiles*] [*ライブラリ*]

/DEF を指定すると、lib は LIB コマンドで渡されるエクスポート仕様から出力ファイルを作成します。 エクスポートを指定するには、次の3つの方法を使用することをお勧めします。

1. **`__declspec(dllexport)`** *Objfiles*または*ライブラリ*の1つの定義

1. LIB コマンドラインでの/EXPORT:*name*の指定

1. *Deffile*内の**エクスポート**ステートメント内の定義

これらは、エクスポートプログラムをリンクするときにエクスポートを指定するために使用するのと同じ方法です。 プログラムでは、複数のメソッドを使用できます。 Lib コマンドの一部 (複数の*objfiles*や/export 仕様など) は、リンクコマンドの場合と同様に、lib コマンドでコマンドファイルに指定できます。

インポートライブラリとエクスポートファイルのビルドには、次のオプションが適用されます。

> **/Out:** *インポート*

作成される*インポート*ライブラリの既定の出力ファイル名を上書きします。 /OUT が指定されていない場合、既定の名前は、LIB コマンド内の最初のオブジェクトファイルまたはライブラリのベース名と拡張子 .lib です。 エクスポートファイルには、インポートライブラリと拡張子 .exp と同じ基本名が付けられます。

> **/Export:** *entryname* \[ **=** *internalname*] \[ , **\@** <em>序数</em> \[ , **NONAME**]] \[ ,**データ**]

プログラムから関数をエクスポートして、他のプログラムが関数を呼び出せるようにします。 データは、**データ**キーワードを使用してエクスポートすることもできます。 通常、エクスポートは DLL で定義されます。

*Entryname*は、呼び出し元のプログラムによって使用される関数またはデータ項目の名前です。 必要に応じて、定義プログラムで認識されている関数として*internalname*を指定できます。既定では、 *internalname*は*entryname*と同じです。 *序数*では、1 ~ 65535 の範囲のエクスポートテーブルのインデックスを指定します。*序数*を指定しない場合、LIB は1を割り当てます。 Entryname**キーワードを**使用すると、関数は序数として*entryname*のみエクスポートされます。 データ**キーワードは**、データのみのオブジェクトをエクスポートするために使用されます。

> **/INCLUDE:** *シンボル*

指定された*記号*をシンボルテーブルに追加します。 このオプションは、含まれないライブラリオブジェクトを強制的に使用する場合に便利です。

準備手順でインポートライブラリを作成する場合は、.dll を作成する前に、.dll をビルドするときに、インポートライブラリのビルド時に渡されたものと同じオブジェクトファイルのセットを渡す必要があることに注意してください。

## <a name="see-also"></a>関連項目

[インポート ライブラリとエクスポート ファイル](working-with-import-libraries-and-export-files.md)
