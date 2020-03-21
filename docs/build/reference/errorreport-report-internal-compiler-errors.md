---
title: /errorReport (内部コンパイラ エラーの報告)
description: Microsoft C/C++コンパイラ/errorreport コマンドラインオプションのリファレンスです。
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
ms.openlocfilehash: 9efe96ed2611795e1fef408ad07b49d65261c3b1
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075078"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (内部コンパイラ エラーの報告)

> [!NOTE]
> **/Errorreport**オプションは非推奨とされます。 Windows Vista 以降では、エラー報告は[Windows エラー報告 (WER)](/windows/win32/wer/windows-error-reporting)設定によって制御されます。

## <a name="syntax"></a>構文

> **/errorreport:** \[**none** \| **prompt** \| **queue** \| **send** ]

## <a name="remarks"></a>解説

内部コンパイラエラー (ICE) は、コンパイラがソースコードファイルを処理できない場合に発生します。 ICE が発生した場合、コンパイラは出力ファイルを生成しないか、コードの修正に使用できる有用な診断を生成しません。

**/Errorreport**引数は、Windows エラー報告サービスの設定によってオーバーライドされます。 レポートが Windows エラー報告によって有効になっている場合、コンパイラは内部エラーのレポートを Microsoft に自動的に送信します。 Windows エラー報告で無効になっている場合、レポートは送信されません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. **[構成プロパティ]**  > [ **CC++ /**  > **詳細設定**] プロパティページを開きます。

1. **エラー報告**のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>) をご覧ください。

## <a name="see-also"></a>参照

[MSVC コンパイラオプション](compiler-options.md)\
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
