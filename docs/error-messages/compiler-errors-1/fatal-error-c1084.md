---
description: '詳細情報: 致命的なエラー C1084'
title: 致命的なエラー C1084
ms.date: 11/04/2016
f1_keywords:
- C1084
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
ms.openlocfilehash: 6a3221bb894c0b320642a923d9552a207a2ff9ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145315"
---
# <a name="fatal-error-c1084"></a>致命的なエラー C1084

filetype ファイルを読み取れません。'file': message

このエラーは一般的に、コンパイラによって行われた内部的なシステム API 呼び出しの失敗によって発生します。 このエラーが発生したときに表示されるメッセージは、 [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) または [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage)のいずれかによって生成されることがよくあります。

次の手順を実行すると、C1084 の解決に役立つ場合があります。

- 指定したファイルが存在することを確認します。

- 指定したファイルにアクセスするための適切なアクセス許可が設定されていることを確認します。

- コマンドライン構文が、「 [コンパイラ Command-Line 構文](../../build/reference/compiler-command-line-syntax.md)」に記載されている規則に従っていることを確認します。

- 環境変数 **TMP** と **TEMP** が適切に設定されていること、およびこれらの環境変数が参照するディレクトリにアクセスするための適切なアクセス許可があることを確認します。 また、 **TMP** および **TEMP** 環境変数によって参照されるドライブに、十分な空き領域があることを確認します。

- "ファイル番号が正しくありません" というメッセージが表示される場合は、指定したファイルがバックグラウンドでのコンパイル中にフォアグラウンドで閉じられている可能性があります。

上記の診断を実行した後、クリーン ビルドを実行します。
