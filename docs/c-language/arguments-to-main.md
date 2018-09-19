---
title: main の引数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98216f9e7354d9699bcaf74430028c88130c97e6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060903"
---
# <a name="arguments-to-main"></a>main の引数

**ANSI 2.1.2.2.1** main への引数のセマンティクス

Microsoft C では、プログラムの起動時に呼び出される関数は **main** と呼ばれます。 **main** に対して宣言されるプロトタイプはなく、0 個、2 個、または 3 個のパラメーターで定義できます。

```
int main( void )
int main( int argc, char *argv[] )
int main( int argc, char *argv[], char *envp[] )
```

上記の 3 行目は、ANSI C 標準に対する Microsoft の拡張機能であり、**main** は 3 つのパラメーターを受け入れています。 3 番目のパラメーター **envp** は、環境変数へのポインターの配列です。 **envp** 配列は、null ポインターで終了します。 **main** および **envp** の詳細については、「[main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)」を参照してください。

変数 **argc** が負の値を持つことはありません。

文字列の配列は **argv[argc]** で終わります (ここに null ポインターが含まれています)。

**argv** 配列のすべての要素は、文字列へのポインターです。

コマンド ライン引数なしで呼び出されたプログラムは、実行可能ファイルの名前が **argv[0]** に配置されるため、**argc** の値 1 を受け取ります。 (MS-DOS 3.0 より前のバージョンでは、実行可能ファイルの名前は使用できません。 **argv[0]** には文字 "C" が配置されます)。**argv[1]** から **argv[argc - 1]** によってポイントされる文字列が、プログラム パラメーターになります。

パラメーター **argc** と **argv** は変更可能で、プログラムの起動と終了の間で最後に格納した値を保持します。

## <a name="see-also"></a>参照

[環境](../c-language/environment.md)