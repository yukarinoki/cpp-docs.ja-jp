---
title: 引数の説明 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- envp argument
- main function, syntax
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 91c2cbe3-9aca-4277-afa1-6137eb8fb704
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f79f8648c2c0d12bf521c38e2db025a8841ab927
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061085"
---
# <a name="argument-description"></a>引数の説明

**main** 関数および**wmain** 関数の `argc` パラメーターは、コマンド ラインからプログラムに渡される引数の数を指定する整数です。 プログラム名は引数と見なされるため、`argc` の値は 1 以上です。

## <a name="remarks"></a>コメント

`argv` パラメーターは、プログラム引数を表す null で終わる文字列へのポインターの配列です。 配列の各要素は、**main** (または **wmain**) に渡された引数の文字列表現を指します (配列については、「[配列の宣言](../c-language/array-declarations.md)」を参照)。`argv` パラメーターは、`char` 型 (`char *argv[]`) へのポインターの配列として、または `char` 型 (`char **argv`) へのポインターへのポインターとして宣言できます。 **wmain** の場合、`argv` パラメーターは `wchar_t` (`wchar_t *argv[]`) 型へのポインターの配列として、または `wchar_t` (`wchar_t **argv`) 型へポインターへのポインターとして宣言できます。

慣例では、`argv`**[0]** は、プログラムが起動されるコマンドです。  ただし、[CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) を使用してプロセスを実行することはできません。また、1 つ目と 2 つ目の引数 (`lpApplicationName` と `lpCommandLine`) を使用する場合、`argv`**[0]** は実行可能ファイルの名前になるとは限りません。実行可能ファイルの名前を取得するには [GetModuleFileName](https://msdn.microsoft.com/library/windows/desktop/ms683197) を使用します。

最後のポインター (`argv[argc]`) は **NULL** です (環境変数の情報を取得する代替メソッドについては、「*ランタイム ライブラリ リファレンス*」の「[getenv](../c-runtime-library/reference/getenv-wgetenv.md)」を参照)。

**Microsoft 固有の仕様**

`envp` パラメーターは、ユーザーの環境変数の値セットを表す null で終了する文字列の配列へのポインターです。 `envp` パラメーターは、`char` (`char *envp[]`) へのポインターの配列として、または `char` (`char **envp`) へのポインターへのポインターとして宣言できます。 **wmain** 関数で、`envp` パラメーターは `wchar_t` (`wchar_t *envp[]`) へのポインターの配列として、または `wchar_t` (`wchar_t **envp`) へのポインターとして宣言できます。 配列の末尾は **NULL** \* ポインターによって示されます。 **main** または **wmain** に渡される環境ブロックは、現在の環境の "固定の" コピーであることに注意してください。 その後 _**putenv** か `_wputenv` の呼び出しによって環境を変更する場合、`getenv`/`_wgetenv` と `_environ` または `_wenviron` の変数が返す現在の環境は変わりますが、`envp` が指すブロックは変わりません。 `envp` パラメーターは C では ANSI 互換ですが、C++ では非互換です。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)