---
description: 詳細については、「プロジェクトビルドエラー PRJ0003」を参照してください。
title: プロジェクト ビルド エラー PRJ0003
ms.date: 11/04/2016
f1_keywords:
- PRJ0003
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
ms.openlocfilehash: b5ca521bdddb78c3cd7c5dd41f8999b99cb92e20
ms.sourcegitcommit: 6183207b11575d7b44ebd7c18918e916a0d8c63d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "97951438"
---
# <a name="project-build-error-prj0003"></a>プロジェクト ビルド エラー PRJ0003

> '*コマンドライン*' を生成中にエラーが発生します。

[**プロパティページ**] ダイアログボックスの入力から作成された *コマンドライン* コマンドがエラーコードを返しましたが、**出力** ウィンドウに情報が表示されません。

このエラーの考えられる原因は次のとおりです。

- プロジェクトは ATL サーバーに依存します。 Visual Studio 2008 以降、ATL Server は Visual Studio の一部としては含まれなくなりましたが、CodePlex では共有ソースプロジェクトとしてリリースされています。 ATL サーバーのソースコードとツールをダウンロードするには、 [Atl サーバーライブラリとツール](https://archive.codeplex.com/?p=atlserver)に関するページを参照してください。

- システムリソースが不足しています。 これを解決するには、いくつかのアプリケーションを閉じてください。

- セキュリティ特権が不足しています。 十分なセキュリティ特権があることを確認します。

- **VC + + ディレクトリ** に指定された実行可能ファイルのパスには、実行しようとしているツールのパスは含まれません。 詳細については、「[コンパイラとビルドのプロパティの設定](../../build/working-with-project-properties.md)」を参照してください。

- メイクファイルプロジェクトの場合、 **ビルドコマンドライン** または **リビルドコマンドライン** のいずれかで実行するコマンドがありません。

## <a name="see-also"></a>関連項目

[プロジェクトのビルドエラーと警告 (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
