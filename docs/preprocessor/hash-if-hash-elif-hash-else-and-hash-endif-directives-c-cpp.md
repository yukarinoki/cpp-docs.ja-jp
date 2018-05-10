---
title: '#場合、#elif、#else、および #endif ディレクティブ (C/C++) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#else'
- '#endif'
- '#if'
- '#elif'
- defined
- __has_include
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9d4f941298159b8a3ea1aa3fe37efd1e6dc68ab
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if、#elif、#else、および #endif ディレクティブ (C/C++)
`#if` ディレクティブは、`#elif`、`#else`、および `#endif` ディレクティブと共にソース ファイルの各部分のコンパイルを制御します。 `#if` の後に記述した式がゼロ以外の値になる場合、`#if` ディレクティブの直後の一連の行が翻訳単位として保持されます。  
  
## <a name="grammar"></a>文法  
 *条件付き*:  
 *if 部分 elif パーツ*opt*else 部分*opt*endif 行*  
  
 *if 部分*:  
 *場合に行のテキスト*  
  
 *if 行*:  
 **#if**  *constant-expression*  
  
 **#ifdef**  *identifier*  
  
 **#ifndef**  *identifier*  
  
 *elif パーツ*:  
 *elif 行のテキスト*  
  
 *elif パーツ elif 行テキスト*  
  
 *elif 行*:  
 **#elif**  *constant-expression*  
  
 *他の部分から成る*:  
 *else 行のテキスト*  
  
 *else 行*:  
 `#else`  
  
 *endif 行*:  
 `#endif`  
  
 ソース ファイルの各 `#if` ディレクティブは `#endif` 終了ディレクティブと対応している必要があります。 `#elif` ディレクティブと `#if` ディレクティブの間に、`#endif` ディレクティブはいくつでも記述できますが、`#else` ディレクティブは 1 つしか記述できません。 `#else` ディレクティブ (存在する場合) は、`#endif` の前の最後のディレクティブである必要があります。  
  
 `#if`、`#elif`、`#else`、および `#endif` ディレクティブは、他の `#if` ディレクティブのテキスト部分に入れ子にできます。 入れ子になった `#else`、`#elif`、または `#endif` ディレクティブは、最も近い先行する `#if` ディレクティブに属します。  
  
 すべての条件付きコンパイル ディレクティブなど`#if`と **#ifdef**、終了と一致する必要があります`#endif`ディレクティブ ファイルの末尾です。 前に、エラー メッセージを生成するそれ以外の場合。 条件付きコンパイル ディレクティブがインクルード ファイルに含まれている場合も同じ条件を満たす必要があります。つまり、インクルード ファイルの終わりに対になる条件付きコンパイル ディレクティブが必要です。  
  
 次のコマンド行の一部内でマクロ置換は実行、`#elif`コマンド、マクロの呼び出しで使用できるように、*定数式*です。  
  
 プリプロセッサが出現する特定の 1 つを選択*テキスト*さらに処理します。 指定されたブロック*テキスト*テキストのシーケンスを指定できます。 複数行にまたがる場合があります。 通常*テキスト*コンパイラまたはプリプロセッサに対して意味を持つプログラム テキストです。  
  
 プリプロセッサは、選択した処理*テキスト*コンパイラに渡します。 場合*テキスト*プリプロセッサ ディレクティブ、プリプロセッサはそれらのディレクティブが含まれています。 プリプロセッサによって選択されたテキスト ブロックだけがコンパイルされます。  
  
 プリプロセッサは、1 つを選択*テキスト*各定数式を評価することによって項目`#if`または`#elif`ディレクティブ true (ゼロ以外) の定数式が見つかるまでです。 すべてのテキストを選択 (以降での他のプリプロセッサ ディレクティブを含む**#**)、関連するまで`#elif`、 `#else`、または`#endif`です。  
  
 場合のすべての出現*定数式*が false の場合、いない場合、または`#elif`ディレクティブが表示されて、プリプロセッサは、後のテキスト ブロックを選択、`#else`句。 場合、`#else`句を省略するのすべてのインスタンス*定数式*で、`#if`ブロックは、false、テキスト ブロックが選択されていません。  
  
 *定数式*これら追加の制限により整数定数式です。  
  
-   式が整数型である必要があり、文字定数、整数定数のみを含めることができます、**定義**演算子。  
  
-   この式は `sizeof` または型キャスト演算子を使用できません。  
  
-   ターゲット環境は整数のすべての範囲を表現できるとは限りません。  
  
-   翻訳は、型を表す`int`型と同じ**長い**、および`unsigned int`と同じ`unsigned long`です。  
  
-   トランスレーターは、ターゲット環境とは別のコード値のセットに文字定数を翻訳できます。 ターゲット環境のプロパティを調べるには、ターゲット環境向けにビルドされたアプリケーションで LIMITS.H からマクロの値を確認します。  
  
-   この式は、環境に関する照会を実行できないように、ターゲット コンピューターの実装の詳細から分離しておく必要があります。  

## <a name="defined"></a>定義  
 プリプロセッサ演算子**定義**次の構文に示すように、特殊な定数式で使用できます。  
  
 defined( `identifier` )  
  
 defined `identifier`  
  
 この定数式は true (ゼロ以外) と見なされます、*識別子*現在定義されているか。 それ以外の場合、条件が false (0) です。 空のテキストとして定義された識別子は、定義されていると見なされます。 **定義**でディレクティブを使用することができます、`#if`と`#elif`ディレクティブが、これ以外の場所。  
  
 次の例では、`#if` と `#endif` のディレクティブが、3 つの関数呼び出しの 1 つに対するコンパイルを制御します。  
  
```  
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
  
```  
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
  
 最初の `#if` ブロックには、`#if`、`#else`、`#endif` ディレクティブの 2 セットが入れ子になっています。 最初のセットのディレクティブは、`DLEVEL > 5` が true の場合にのみ処理されます。 それ以外の場合、# の後にあるステートメント**else**処理されます。  
  
 2 つ目のブロックでは、`#elif` ディレクティブと `#else` ディレクティブを使用して、`DLEVEL` の値に基づいて 4 つの選択肢のいずれかが選択されるようにしています。 `STACK` の定義により、定数 `DLEVEL` は 0、100、または 200 に設定されます。 `DLEVEL` が 5 より大きい場合、次のステートメントがコンパイルされます。  
  
```  
#elif DLEVEL > 5  
display(debugptr);  
```  
  
 この場合、`STACK` は定義されません。  
  
 条件付きコンパイルの一般的な用途は、同じヘッダー ファイルの多重インクルードを防ぐことです。 C++ では、クラスをヘッダー ファイルで定義することが多いため、多重定義を防ぐために次のようなコンストラクターを使用できます。  
  
```  
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
**Visual Studio 2017 15.3 およびそれ以降のバージョン**: ライブラリのヘッダーが追加できるかどうかを判断します。  

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