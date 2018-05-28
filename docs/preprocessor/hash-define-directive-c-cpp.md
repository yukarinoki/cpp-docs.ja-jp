---
title: '#define ディレクティブ (C/C++) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#define'
dev_langs:
- C++
helpviewer_keywords:
- define directive (#define), syntax
- preprocessor, directives
- define directive (#define)
- '#define directive, syntax'
- '#define directive'
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8875c2b2c744a16f936fd2220826f23413a0e6c9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="define-directive-cc"></a>#define ディレクティブ (C/C++)
`#define`を作成、*マクロ*、識別子またはパラメーター化された識別子トークン文字列との関連付けであります。 マクロが定義されると、コンパイラはそれ以降にソース ファイル内に識別子が見つかるたびに、トークン文字列に置き換えることができます。  
  
## <a name="syntax"></a>構文  
 `#define` *identifier* *token-string*opt  
  
 `#define` *識別子* `(` *識別子*opt`,`*しています.* `,`*識別子*opt`)`*トークン文字列*オプトイン  
  
## <a name="remarks"></a>コメント  
 `#define`の代わりにコンパイラがディレクティブ*トークン文字列*たびに*識別子*ソース ファイルにします。 *識別子*トークンを形成時にのみ置き換えられます。 つまり、*識別子*コメント、または長い識別子の一部として、文字列内に表示される場合は置き換えられません。 詳細については、次を参照してください。[トークン](../cpp/tokens-cpp.md)です。  
  
 *トークン文字列*キーワード、定数、または完全なステートメントなどのトークンの一連の引数で構成されます。 1 つ以上の空白文字で区切る必要があります*トークン文字列*から*識別子*です。 この空白は、置き換えられるテキストの一部とは見なされません。最後のトークンのテキストに続く空白も同様です。  
  
 A`#define`せず、*トークン文字列*の出現を削除*識別子*ソース ファイルからです。 *識別子*は定義されているを使用してテストすることができます、`#if defined`と`#ifdef`ディレクティブです。  
  
 2 番目の構文形式は、パラメーターを受け取る関数に似たマクロを定義します。 この形式では、かっこで囲んだパラメーターのリストを使用できます (省略可能)。 マクロが定義されている、以降の各出現する位置の後に*識別子*(*識別子*選択...,*識別子*opt) のバージョンに置き換えられます、 *トークン文字列*仮パラメーターを置き換える実際の引数を持つ引数。  
  
 仮パラメーター名に表示されます*トークン文字列*を実際の値が置き換えられる場所をマークします。 各パラメーターの名前を複数回現れ*トークン文字列*名前は、任意の順序で表示されることができます。 呼び出しにある引数の数は、マクロ定義にあるパラメーターの数に一致する必要があります。 かっこを多めに使用することで、複雑な実引数が正しく解釈されるようにできます。  
  
 リスト内で仮パラメーターはコンマで区切ります。 リストの各名前は一意である必要があり、リストはかっこで囲む必要があります。 スペースを分離できます*識別子*し、開きかっこを入力します。 行の連結を使用する — 円記号の配置 (`\`)、改行文字の直前に — 複数のソース行に長いディレクティブのです。 新しい行を終了するまでの仮パラメーター名のスコープ*トークン文字列*です。  
  
 マクロが 2 番目の構文形式で定義されると、それ以降の引数リストまでのテキスト インスタンスがマクロの呼び出しを示します。 インスタンスに続く実際の引数*識別子*ソース ファイルで、マクロ定義に対応する仮パラメーターに照合されます。 それぞれの仮パラメーター*トークン文字列*、文字列化する前がない (`#`)、文字定数化 (`#@`)、またはトークン連結 (`##`) 演算子、続かないまたは、`##`演算子は、対応する実引数によって置き換えられます。 ディレクティブが仮パラメーターを置き換える前に、実引数内のすべてのマクロが展開されます  (演算子については、「[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md))。  
  
 引数を受け取るマクロの次の例では、`#define` の 2 番目の構文形式を示しています。  
  
```  
// Macro to define cursor lines   
#define CURSOR(top, bottom) (((top) << 8) | (bottom))  
  
// Macro to get a random integer with a specified range   
#define getrandom(min, max) \  
    ((rand()%(int)(((max) + 1)-(min)))+ (min))  
```  
  
 副作用のある引数が原因で、マクロが予期しない結果を生成することがあります。 指定された正式なパラメーターで 1 つ以上の時間が表示される*トークン文字列*です。 その仮パラメーターが副作用のある式と置き換えられると、その式は、その副作用と共に、複数回評価される場合があります  (下の例を参照してください[トークン連結演算子 (##)](../preprocessor/token-pasting-operator-hash-hash.md))。  
  
 `#undef` ディレクティブは、識別子のプリプロセッサ定義を未定義の状態にします。 参照してください[#undef ディレクティブ](../preprocessor/hash-undef-directive-c-cpp.md)詳細についてはします。  
  
 定義されたマクロの名前が発生したかどうかは*トークン文字列*(でも別マクロの展開)、結果として展開されていません。  
  
 同じ名前のマクロの 2 番目の `#define` は、2 番目のトークン シーケンスが最初のものと同じでなければ、警告を生成します。  
  
 **Microsoft 固有の仕様**  
  
 Microsoft C/C++ では、新しい定義が元の定義と構文的に同一の場合、マクロを再定義できます。 つまり、2 つの定義に異なるパラメーター名を付けることができます。 この動作は、2 つの定義が語彙的に同一である必要がある [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] C とは異なります。  
  
 たとえば、次の 2 つのマクロは、パラメーター名を除いて同一です。 [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] C では、このような再定義することはできませんが、Microsoft C/C エラーなしでコンパイルします。  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( a1 * a2 )  
```  
  
 一方、次の 2 つのマクロは同一ではなく、Microsoft C/C++ で警告が生成されます。  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( b1 * b2 )  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
 `#define` ディレクティブの例を次に示します。  
  
```  
#define WIDTH       80  
#define LENGTH      ( WIDTH + 10 )  
```  
  
 最初のステートメントは識別子 `WIDTH` を整数定数 80 として定義し、`LENGTH` と整数定数 10 に基づき `WIDTH` を定義します。 `LENGTH` は見つかるたびに (`WIDTH + 10`) に置き換えられます。 次に、`WIDTH + 10` は見つかるたびに式 (`80 + 10`) に置き換えられます。 `WIDTH + 10` を囲むかっこは、次のようなステートメントの解釈を制御するため重要です。  
  
```  
var = LENGTH * 20;  
```  
  
 プロプロセス段階が終了すると、ステートメントは次のようになります。  
  
```  
var = ( 80 + 10 ) * 20;  
```  
  
 1800 に評価されます。 かっこがない場合、結果は次のようになります。  
  
```  
var = 80 + 10 * 20;  
```  
  
 これは、280 に評価されます。  
  
 **Microsoft 固有の仕様**  
  
 マクロおよび定数の定義、 [/D](../build/reference/d-preprocessor-definitions.md)コンパイラ オプションを使用すると同じ効果を持つ、`#define`プリプロセッサ ディレクティブは、ファイルの先頭にします。 /D オプションを使用して最大 30 個のマクロを定義できます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)