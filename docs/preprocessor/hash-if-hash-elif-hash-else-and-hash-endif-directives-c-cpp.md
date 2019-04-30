---
title: '#場合、#elif、#else、および #endif ディレクティブ (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#else'
- '#endif'
- '#if'
- '#elif'
- defined
- __has_include
helpviewer_keywords:
- '#elif directive'
- conditional compilation, directives
- endif directive (#endif)
- preprocessor, directives
- '#else directive'
- '#endif directive'
- if directive (#if)
- else directive (#else)
- '#if directive'
- elif directive (#elif)
- defined directive
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
ms.openlocfilehash: 90fbab45c6408c30198c2a52a42545718002cc11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409890"
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if、#elif、#else、および #endif ディレクティブ (C/C++)

**#If**ディレクティブ、 **#elif**、 **#else**、および **#endif**ディレクティブでは、ソース ファイルの一部のコントロールのコンパイル。 式を記述する場合 (後に、 **#if**) の直後に続く行グループ、0 以外の値を持つ、 **#if**ディレクティブは、翻訳単位に保持されます。

## <a name="grammar"></a>文法

*条件付き*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif の構成要素の if 部分*<sub>opt</sub> *else 部分*<sub>opt</sub> *endif 行*

*if 部分*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*if 行のテキスト*

*if 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#if**  *constant-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifdef**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#ifndef**  *identifier*

*elif パーツ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif 行のテキスト*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*elif パーツ elif 行のテキスト*

*elif 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#elif**  *constant-expression*

*他の部分から成る*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*他の行のテキスト*

*他の行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#else**

*endif 行*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**#endif**

各 **#if**ソース ファイルのディレクティブを終了して一致する必要が **#endif**ディレクティブ。 任意の数の **#elif**間ディレクティブを表示できる、 **#if**と **#endif**ディレクティブでは、最大で 1 つが、 **#else**ディレクティブを使用します。 **#Else**ディレクティブ、存在する場合は前に、の最後のディレクティブ **#endif**します。

**#If**、 **#elif**、 **#else**、および **#endif**ディレクティブを他のテキストの部分に入れ子 **#if**ディレクティブ。 入れ子になった **#else**、 **#elif**、または **#endif** 、最も近い先行するディレクティブが属している **#if**ディレクティブ。

すべての条件付きコンパイル ディレクティブなど **#if**と **#ifdef**、終了と一致する必要があります **#endif**ディレクティブは、最後のファイルの前にそれ以外の場合、エラーメッセージが生成されます。 条件付きコンパイル ディレクティブが含まれている場合は、インクルード ファイルが同じ条件を満たす必要があります。インクルード ファイルの最後に一致しない条件付きコンパイル ディレクティブがありません。

マクロ置換は、次のコマンドラインの一部内で実行されます、 **#elif**コマンド、マクロの呼び出しで使用できるように、*定数式*します。

プリプロセッサは指定した出現を 1 つを選択*テキスト*さらに処理します。 指定されたブロック*テキスト*テキストのシーケンスを指定できます。 複数行にまたがる場合があります。 通常、*テキスト*はコンパイラまたはプリプロセッサに対して意味を持つプログラム テキストです。

プリプロセッサは、選択した処理*テキスト*をコンパイラに渡します。 場合*テキスト*プリプロセッサはそれらのディレクティブのプリプロセッサ ディレクティブが含まれています。 プリプロセッサによって選択されたテキスト ブロックだけがコンパイルされます。

プリプロセッサは、1 つを選択します*テキスト*続く定数式を評価することによって項目 **#if**または **#elif** true (0 以外) の定数が見つかるまでディレクティブ。式。 すべてのテキストを選択します (以降では他のプリプロセッサ ディレクティブを含む**#**) それに関連付けられた最大 **#elif**、 **#else**、または **#endif**.

場合のすべての出現箇所*定数式*が false の場合、いない場合または **#elif**ディレクティブの表示をプリプロセッサが後のテキスト ブロックを選択して、 **#else**句。 場合、 **#else**句を省略するのすべてのインスタンス*定数式*で、 **#if**が false のブロック、テキスト ブロックが選択されていません。

*定数式*これら 追加の制約付き整数定数式です。

- 式が整数型である必要があり、文字定数、整数定数のみを含めることができます、**定義**演算子。

- この式は `sizeof` または型キャスト演算子を使用できません。

- ターゲット環境は整数のすべての範囲を表現できるとは限りません。

- 翻訳は、型を表す**int**型と同じ**長い**と**符号なし int**と同じ**unsigned long**します。

- トランスレーターは、ターゲット環境とは別のコード値のセットに文字定数を翻訳できます。 ターゲット環境のプロパティを調べるには、ターゲット環境向けにビルドされたアプリケーションで LIMITS.H からマクロの値を確認します。

- この式は、環境に関する照会を実行できないように、ターゲット コンピューターの実装の詳細から分離しておく必要があります。

## <a name="defined"></a>定義

プリプロセッサ演算子**定義**次の構文に示すように、特別な定数式で使用できます。

defined( `identifier` )

defined `identifier`

この定数式が場合は true (0 以外) と見なされる、*識別子*現在定義されているか。 それ以外の場合、条件が false (0)。 空のテキストとして定義された識別子は、定義されていると見なされます。 **定義**にディレクティブを使用することができます、 **#if**と **#elif**ディレクティブが、これ以外の場所。

次の例では、 **#if**と **#endif**ディレクティブは、次の 3 つの関数呼び出しのいずれかのコンパイルを制御します。

```C
#if defined(CREDIT)
    credit();
#elif defined(DEBIT)
    debit();
#else
    printerror();
#endif
```

`credit` の関数呼び出しは、`CREDIT` 識別子が定義されている場合、コンパイルされます。 `DEBIT` 識別子が定義されている場合、`debit` の関数呼び出しがコンパイルされます。 どちらの識別子も定義されていない場合、`printerror` の呼び出しがコンパイルされます。 `CREDIT` と `credit` は、大文字小文字が異なるため、C および C++ で別々の識別子になることに注意してください。

次の例の条件付きコンパイル ステートメントは、`DLEVEL` というシンボリック定数が定義済みとします。

```C
#if DLEVEL > 5
    #define SIGNAL  1
    #if STACKUSE == 1
        #define STACK   200
    #else
        #define STACK   100
    #endif
#else
    #define SIGNAL  0
    #if STACKUSE == 1
        #define STACK   100
    #else
        #define STACK   50
    #endif
#endif
#if DLEVEL == 0
    #define STACK 0
#elif DLEVEL == 1
    #define STACK 100
#elif DLEVEL > 5
    display( debugptr );
#else
    #define STACK 200
#endif
```

最初の **#if**ブロックは、2 つのセットを示しています。 入れ子になった **#if**、 **#else**、および **#endif**ディレクティブ。 最初のセットのディレクティブは、`DLEVEL > 5` が true の場合にのみ処理されます。 それ以外の場合後のステートメント **#else**処理されます。

**#Elif**と **#else** 2 番目の例のディレクティブを使用して、いずれかの値に基づいて、4 つの選択肢`DLEVEL`します。 `STACK` の定義により、定数 `DLEVEL` は 0、100、または 200 に設定されます。 `DLEVEL` が 5 より大きい場合、次のステートメントがコンパイルされます。

```C
#elif DLEVEL > 5
display(debugptr);
```

この場合、`STACK` は定義されません。

条件付きコンパイルの一般的な用途は、同じヘッダー ファイルの多重インクルードを防ぐことです。 C++ では、クラスをヘッダー ファイルで定義することが多いため、多重定義を防ぐために次のようなコンストラクターを使用できます。

```cpp
/*  EXAMPLE.H - Example header file  */
#if !defined( EXAMPLE_H )
#define EXAMPLE_H

class Example
{
...
};

#endif // !defined( EXAMPLE_H )
```

前のコードは、シンボリック定数 `EXAMPLE_H` が定義されているかどうかを確認します。 定義されている場合、ヘッダー ファイルは既にインクルードされており、再処理する必要はありません。 定義されていない場合、EXAMPLE.H が処理されてから、`EXAMPLE_H` が処理済みとマークされます。

## <a name="hasinclude"></a>__has_include

**Visual Studio 2017 バージョン 15.3 およびそれ以降**:ライブラリのヘッダーが含めることができるかどうかを決定します。

```cpp
#ifdef __has_include
#  if __has_include(<filesystem>)
#    include <filesystem>
#    define have_filesystem 1
#  elif __has_include(<experimental/filesystem>)
#    include <experimental/filesystem>
#    define have_filesystem 1
#    define experimental_filesystem
#  else
#    define have_filesystem 0
#  endif
#endif
```

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)