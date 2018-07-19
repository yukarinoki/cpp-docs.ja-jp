---
title: CLR 列挙型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scope, of CLR enum
- enum struct keyword [C++]
- enum class keyword [C++]
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2416a306373db08c5e925b4987fc8a9273973c39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111498"
---
# <a name="clr-enum-type"></a>CLR 列挙型
列挙型の動作と宣言が変更されたマネージ拡張から C++ の Visual C にします。  
  
 マネージ拡張 enum 宣言の後、`__value`キーワード。 派生する CLR 列挙型からネイティブ列挙型を区別するためには、この考え方`System::ValueType`、類似の機能を提案されているときにします。 例えば:  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};  
```  
  
 新しい構文は、その値型のルートではなく、後者のクラスの性質を強調することで、CLR 列挙型と区別するネイティブの問題を解決します。 そのため、`__value`キーワードを破棄するのスペース区切りキーワードの組み合わせに置き換えられます`enum class`です。 これは、参照、値、およびインターフェイス クラスの宣言にキーワード ペア対称を提供します。  
  
```  
enum class ec;  
value class vc;  
ref class rc;  
interface class ic;  
```  
  
 列挙型のペアの翻訳`e1`と`e2`新しい構文では次のとおり。  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 この小さな構文変更とは別には、CLR 列挙型の動作をさまざまな方法で変更されています。  
  
-   CLR 列挙型の事前宣言がサポートされていません。 マッピングはありません。 コンパイル時のエラーとしてフラグが単純にします。  
  
```  
__value enum status; // Managed Extensions: ok  
enum class status;   // new syntax: error  
```  
  
-   組み込みの数値型の間でオーバー ロードの解決と`Object`クラスの階層構造に 2 つの言語のバージョン間で戻されました。 副作用として、としては、CLR 列挙型は数値型に不要になった暗黙的に変換します。  
  
-   新しい構文では、CLR 列挙型は、マネージ拡張の場合はそれ自体のスコープを維持します。 以前は、列挙子は列挙型のコンテナーのスコープ内で参照可能でした。 ここで、列挙子は列挙型のスコープ内にカプセル化されます。  
  
## <a name="clr-enums-are-a-kind-of-object"></a>CLR 列挙型は、種類のオブジェクト  
 次のコードがあるとします。  
  
```  
__value enum status { fail, pass };  
  
void f( Object* ){ Console::WriteLine("f(Object)\n"); }  
void f( int ){ Console::WriteLine("f(int)\n"); }  
  
int main()  
{  
   status rslt = fail;  
  
   f( rslt ); // which f is invoked?  
}  
```  
  
 ネイティブの C++ プログラマ自然はオーバー ロードされたは、どのインスタンスの質問に回答`f()`が呼び出されるは、`f(int)`です。 Enum は整数の記号定数と、ここでは優先される標準的な整数の上位変換に含まれています。  実際にはマネージ拡張でこれが、呼び出しが解決されるインスタンスです。 時ではなく、ネイティブ C++ の考え方が、既存の BCL (基本クラス ライブラリ) フレームワークと対話するときにそれらを使用して数、予想外の問題の原因とこれで、`Enum`はクラスから間接的に派生`Object`です。 Visual C の言語設計のインスタンスで`f()`の呼び出されます`f(Object^)`です。  
  
 Visual C を強制する選択した方法では、CLR 列挙型と数値型の間の暗黙的な変換をサポートしていませんです。 これは明示的なキャスト演算の型を CLR 列挙型のオブジェクトの割り当てを要求することを意味します。 そのため、たとえば、指定されました。  
  
```  
void f( int );  
```  
  
 マネージ拡張で、呼び出しのオーバー ロードされた以外の方法として  
  
```  
f( rslt ); // ok: Managed Extensions; error: new syntax  
```  
  
 [ok] とに含まれる値は、`rslt`は整数値に暗黙的に変換します。 Visual c では、この呼び出しは、コンパイルに失敗します。 正常に変換してを変換演算子を挿入する必要があります。  
  
```  
f( safe_cast<int>( rslt )); // ok: new syntax  
```  
  
## <a name="the-scope-of-the-clr-enum-type"></a>CLR 列挙型のスコープ  
 C および C++ 言語の間の変更のいずれかが、C++ では、構造体施設内のスコープを追加します。 C では、構造体は、インターフェイスまたは関連付けられているスコープのいずれかのサポートのない集計、データだけです。 これはかなり部首変更時に、C の言語から、多くの新しい C++ ユーザー向けの頻度の問題が発生しました。 ネイティブと CLR 列挙型間のリレーションシップは似ています。  
  
 マネージ拡張で、しようとしましたネイティブ列挙型内のスコープの欠落をシミュレートするために CLR 列挙型の列挙の弱く挿入された名前を定義します。 これは失敗に終わりました。 この問題は、こうするに流出、グローバル名前空間、名前の衝突を管理するが困難で結果として列挙子です。 新しい構文で CLR 列挙型内でスコープをサポートする他の CLR 言語に最適化おがします。  
  
 これは、CLR 列挙型の列挙子の修飾せずに使用が新しい構文で認識されないことを意味します。 実際の例を見てみましょう。  
  
```  
// Managed Extensions supporting weak injection  
__gc class XDCMake {  
public:  
   __value enum _recognizerEnum {   
      UNDEFINED,  
      OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6,  
   };  
  
   ListDictionary* optionList;  
   ListDictionary* itagList;  
  
   XDCMake() {  
      optionList = new ListDictionary;  
  
      // here are the problems...  
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)  
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)  
  
      itagList = new ListDictionary;  
      itagList->Add(S"returns",   
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)  
   }  
};  
```  
  
 列挙子の名前を使用して、3 つの非修飾 (`(1)`、 `(2)`、および`(3)`) は、ソース コードをコンパイルするために新しい構文を翻訳で修飾する必要があります。 元のソース コードの適切な翻訳を次に示します。  
  
```  
ref class XDCMake {  
public:  
   enum class _recognizerEnum {  
      UNDEFINED, OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6  
   };  
  
   ListDictionary^ optionList;  
   ListDictionary^ itagList;  
  
   XDCMake() {  
      optionList = gcnew ListDictionary;  
      optionList->Add("?",_recognizerEnum::OPTION_USAGE); // (1)  
      optionList->Add("help",_recognizerEnum::OPTION_USAGE); //(2)  
      itagList = gcnew ListDictionary;  
      itagList->Add( "returns",   
         _recognizerEnum::XDC0004_WRN_XML_LOAD_FAILURE); //(3)  
   }  
};  
```  
  
 これは、ネイティブなポートと CLR 列挙型間のデザイン方法を変更します。 Visual C では、関連するスコープを維持する CLR 列挙型、クラス内で列挙型の宣言をカプセル化する効果的なも必要です。 この表現方法と進化しましたベル Laboratories 内 cfront 2.0 の前後にもグローバルな名前の汚染から問題を解決するためにします。  
  
 ベル研究所の Jerry Schwarz によって新しい iostream ライブラリの元のベータ リリースで Jerry でしたをカプセル化しないライブラリ、および一般的な列挙子のように定義されているすべての関連付けられた列挙`read`、 `write`、`append`など、ユーザーが、既存のコードをコンパイルすることがほぼ不可能になっています。 1 つのソリューションがなど、名前に手を加えるが見込めた`io_read`、 `io_write`, などです。2 番目のソリューションれる可能性のある、列挙型のスコープを追加して、言語を変更することがこれ実用的時にします。 中央のソリューションは、クラス内で列挙型をカプセル化するか、クラス階層構造にタグ名と列挙型の列挙子の両方が、外側のクラス スコープを設定する場所)。つまり、クラス内で列挙型を配置するには、少なくとも最初、動機でした哲学がグローバル名前空間の汚染問題への応答を実用的なです。  
  
 Visual C 列挙が不要になったクラス内で列挙型をカプセル化することに説得力のある利点です。 実際には、確認する場合、`System`名前空間、その列挙型、クラス、およびインターフェイスをすべて同じ宣言領域の存在が表示されます。  
  
## <a name="see-also"></a>関連項目  
 [値の型とその動作 (C + + CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [列挙型クラス](../windows/enum-class-cpp-component-extensions.md)