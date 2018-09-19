---
title: 致命的なエラー C1084 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47d56641209ea1fe192bf0c32ace7701a1e579dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054533"
---
# <a name="fatal-error-c1084"></a>致命的なエラー C1084

filetype ファイルを読み取れません。'file': message

このエラーは一般的に、コンパイラによって行われた内部的なシステム API 呼び出しの失敗によって発生します。 このエラーが発生したときに表示されるメッセージがいずれかで生成された多くの場合、 [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)または[FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage)します。

次の手順を実行すると、C1084 の解決に役立つ場合があります。

- 指定したファイルが存在することを確認します。

- 指定したファイルにアクセスするための適切なアクセス許可が設定されていることを確認します。

- コマンドラインの構文で説明する規則に準拠することを確認[コンパイラのコマンドライン構文](../../build/reference/compiler-command-line-syntax.md)します。

- 環境変数を確認**TMP**と**TEMP**をこれらの環境変数が参照されるディレクトリにアクセスするために適切なアクセス許可と同様に、セットでは適切です。 によって参照されているドライブも確認、 **TMP**と**TEMP**環境変数は、十分な量の空き領域を含めることができます。

- "ファイル番号が正しくありません" というメッセージが表示される場合は、指定したファイルがバックグラウンドでのコンパイル中にフォアグラウンドで閉じられている可能性があります。

上記の診断を実行した後、クリーン ビルドを実行します。