---
description: 詳細については、「その他の MSVC ビルドツール」を参照してください。
title: その他の MSVC ビルドツール
ms.date: 08/28/2019
f1_keywords:
- c.build
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
ms.openlocfilehash: 41395edcbc2f375b4173f2cff25cbcac581ee5d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182646"
---
# <a name="additional-msvc-build-tools"></a>その他の MSVC ビルドツール

Visual Studio には、ビルド出力を表示または操作するための次のコマンドラインユーティリティが用意されています。

- [LIB.EXE](lib-reference.md) は、COFF (Common Object File Format) オブジェクトファイルのライブラリを作成および管理するために使用されます。 エクスポートファイルを作成し、エクスポートされた定義を参照するためにライブラリをインポートするために使用することもできます。

- COFF バイナリファイルを変更するには、 [EDITBIN.EXE](editbin-reference.md)を使用します。

- [DUMPBIN.EXE](dumpbin-reference.md) COFF バイナリファイルに関する情報 (シンボルテーブルなど) を表示します。

- [NMAKE](nmake-reference.md) は makefile を読み取り、実行します。

- エラー参照ユーティリティ[ERRLOOK](value-edit-control.md)は、入力された値に基づいてシステムエラーメッセージまたはモジュールエラーメッセージを取得します。

- [XDCMake](xdcmake-reference.md)。 XML タグでマークされたドキュメントコメントを含むソースコードファイルを処理するためのツール。

- [BSCMAKE.EXE](bscmake-reference.md) (旧バージョンとの互換性のためにのみ提供) は、プログラム内のシンボル (クラス、関数、データ、マクロ、および型) に関する情報を含むブラウザー情報ファイル (.bsc) をビルドします。 この情報は、開発環境内の [参照] ウィンドウで表示します。 (.Bsc ファイルは、開発環境でもビルドできます)。

Windows SDK には、 [RC.EXE](/windows/win32/menurc/resource-compiler)を含むいくつかのビルドツールがあります。これは、ダイアログ、プロパティページ、ビットマップ、文字列テーブルなどのネイティブの Windows リソースをコンパイルするために C++ コンパイラによって呼び出されます。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)<br/>
[装飾名](decorated-names.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC リンカー オプション](linker-options.md)
