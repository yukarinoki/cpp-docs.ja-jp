---
description: 詳細については、「Command-Line エラー D8016」を参照してください。
title: コマンド ライン エラー D8016
ms.date: 11/04/2016
f1_keywords:
- D8016
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
ms.openlocfilehash: 2f340cb7574177536310343dc9761058b7b9bc08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115717"
---
# <a name="command-line-error-d8016"></a>コマンド ライン エラー D8016

' オプション 1 ' および ' option2 ' コマンドラインオプションに互換性がありません

コマンドラインオプションを一緒に指定することはできません。

オプションの指定について、CL などの環境変数を確認します。

**/clr** は **/eha** を意味します。 **/clr** で他の任意の **/EH** コンパイラオプションを指定することはできません。 詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

Visual C++ 6.0 プロジェクトを更新した後、D8016 が発生する可能性があります。プロジェクトの更新ウィザードのプロセスでは、プロジェクトの各ソースコードファイルに対して **/rtc** が有効になっている場合があります。これにより、プロジェクトの **/rtc** 設定がオーバーライドされます。  解決するには、プロジェクト内の各ソースコードファイルの **/rtc** 設定を既定の設定に変更します。これは、各ファイルで **/rtc** のプロジェクト設定が有効になることを意味します。

**/Rtc** プロパティの設定を変更する方法については、「 [/Rtc (ランタイムエラーチェック)](../../build/reference/rtc-run-time-error-checks.md) 」を参照してください。
