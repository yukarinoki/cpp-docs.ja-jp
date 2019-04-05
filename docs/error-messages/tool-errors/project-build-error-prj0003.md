---
title: プロジェクト ビルド エラー PRJ0003
ms.date: 11/04/2016
f1_keywords:
- PRJ0003
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
ms.openlocfilehash: 00d101e62d49078ebfcfff9455497f30224b84fe
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039521"
---
# <a name="project-build-error-prj0003"></a>プロジェクト ビルド エラー PRJ0003

> エラーの生成 '*コマンドライン*'。

*コマンドライン*コマンドの形式で入力から、**プロパティ ページ** ダイアログ ボックスに、エラー コードが返されますが表示されます、**出力**ウィンドウ。

このエラーの考えられる理由は次のとおりです。

- プロジェクトは、ATL Server に依存します。 Visual Studio 2008 以降では、ATL Server は、Visual Studio の一部として含めるでされていませんが、CodePlex での共有ソース プロジェクトとしてリリースされています。 ATL Server のソース コードとツールをダウンロードするには[ATL サーバー ライブラリとツール](http://go.microsoft.com/fwlink/p/?linkid=81979)します。

- リソースが不足します。 これを解決する一部のアプリケーションを閉じます。

- セキュリティ特権が不十分です。 セキュリティのための十分な特権があることを確認します。

- 指定された実行可能ファイルのパス**vc++ ディレクトリ**実行しようとしているツールのパスを含めないでください。 詳しくは、次を参照してください[コンパイラを設定し、ビルド プロパティ。](../../build/working-with-project-properties.md)

- メイクファイル プロジェクトでは、どちらかで実行するコマンドがない**ビルド コマンドライン**または**リビルド コマンドライン**します。

## <a name="see-also"></a>関連項目

[プロジェクト ビルド エラーと警告 (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)