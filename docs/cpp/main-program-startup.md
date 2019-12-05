---
title: 'main: プログラムの起動'
ms.date: 11/04/2016
f1_keywords:
- vc.main.startup
- _tmain
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
ms.openlocfilehash: 29e1b77c2e36c66e4e6fc4ec30a73af4d57654a0
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857438"
---
# <a name="main-program-startup"></a>main: プログラムの起動

という名前の特殊な関数**main**はすべての C および C++ プログラムの実行の開始ポイントです。 Unicode プログラミング モデルに準拠するコードを記述する場合は、使用できます`wmain`のワイド文字バージョンである**main**します。

**main**関数がコンパイラによってあらかじめ定義されていません。 これは、プログラム テキストに記述する必要があります。

宣言構文**main**は

```cpp
int main();
```

または、必要に応じて次のように記述します。

```cpp
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft 固有の仕様**

`wmain` の宣言構文は次のとおりです。

```cpp
int wmain( );
```

または、必要に応じて次のように記述します。

```cpp
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

また、tchar.h で定義されている `_tmain`を使用することもできます。 _UNICODE が定義されていない場合、`_tmain` は**メイン**に解決されます。 定義されている場合、`_tmain` は `wmain` に解決されます。

また、 **main**関数と `wmain` 関数は、 **void**を返すように宣言できます (戻り値はありません)。 **Void**を返すように**main**または `wmain` を宣言する場合、 [return](../cpp/return-statement-in-program-termination-cpp.md)ステートメントを使用して、親プロセスまたはオペレーティングシステムに終了コードを返すことはできません。 **Main**または `wmain` が**void**として宣言されている場合に終了コードを返すには、 [exit](../cpp/exit-function.md)関数を使用する必要があります。

**Microsoft 固有の仕様はここまで**

`argc` と `argv` の型は、言語によって定義されています。 名前 `argc`、`argv`、および`envp` は従来のものですが、コンパイラにとって必須ではありません。 詳細と例については、「[引数の定義](../cpp/argument-definitions.md)」を参照してください。

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)<br/>
[main に代わる wmain の使用](../cpp/using-wmain-instead-of-main.md)<br/>
[main 関数に関する制約](../cpp/main-function-restrictions.md)<br/>
[C++ コマンド ライン引数の解析](../cpp/parsing-cpp-command-line-arguments.md)
