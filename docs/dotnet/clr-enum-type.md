---
title: CLR 列挙型 |Microsoft Docs
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
ms.openlocfilehash: a39c451bcff7b5b3b1d7dd9f0d3925616b9d6aab
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436228"
---
# <a name="clr-enum-type"></a>CLR 列挙型

列挙型の動作と宣言がマネージ拡張から変更 C++ 用 Visual C にします。

前に、マネージ拡張列挙型宣言が、`__value`キーワード。 派生する CLR 列挙型からネイティブ列挙型を区別するために、考え方は、 `System::ValueType`、類似の機能の提案中にします。 例えば:

```
__value enum e1 { fail, pass };
public __value enum e2 : unsigned short  {
   not_ok = 1024,
   maybe, ok = 2048
};
```

新しい構文は、その値型のルートではなく、後者のクラスの性質を目立たせることで、ネイティブの区別の問題と CLR 列挙型を解決します。 そのため、`__value`のスペース区切りキーワードの組み合わせに置き換え、キーワードは破棄されます`enum class`します。 これは、参照、値、およびインターフェイス クラスの宣言をペアになっているキーワードの対称性を提供します。

```
enum class ec;
value class vc;
ref class rc;
interface class ic;
```

列挙型のペアの変換は、`e1`と`e2`新しい構文のようになります。

```
enum class e1 { fail, pass };
public enum class e2 : unsigned short {
   not_ok = 1024,
   maybe, ok = 2048
};
```

この小さなの構文の変更とは別には、さまざまな方法で CLR 列挙型の動作を変更されています。

- CLR 列挙型の事前宣言がサポートされていません。 マッピングはありません。 コンパイル時エラーとしてフラグが付きだけです。

```
__value enum status; // Managed Extensions: ok
enum class status;   // new syntax: error
```

- 組み込み数値型の間でオーバー ロードの解決と`Object`2 つの言語のバージョン間のクラス階層に戻されました。 、副作用として、CLR 列挙型は数値型に変換されなく暗黙的にされます。

- 新しい構文では、CLR 列挙型は、独自のスコープでは、マネージ拡張でそうでないを維持します。 以前は、列挙子が列挙型のコンテナーのスコープ内で参照できます。 次に、列挙子は列挙型のスコープ内にカプセル化します。

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

ネイティブの C++ プログラマの自然対数はのどのオーバー ロードされたインスタンスの質問に回答`f()`が呼び出されるは、`f(int)`します。 Enum は整数の記号定数と、この場合も優先される標準的な整数の上位変換に含まれています。  実際にマネージ拡張でこれが、呼び出しが解決されるインスタンス。 時ではなく、ネイティブ C++ の考え方が BCL (基本クラス ライブラリ) の既存のフレームワークと対話するときにそれらを使用して、予想外の問題の数がこれが原因で、`Enum`はクラスから間接的に派生`Object`します。 Visual C の言語設計のインスタンスで`f()`の呼び出されます`f(Object^)`します。

これを強制する Visual C が選択した方法では、CLR の列挙型と数値型の間の暗黙的な変換をサポートしていませんです。 これは、明示的なキャスト演算の型を CLR 列挙型のオブジェクトの割り当てを必要とすることを意味します。 そのため、たとえば、指定されました。

```
void f( int );
```

オーバー ロードされていないメソッドを呼び出し、マネージ拡張として

```
f( rslt ); // ok: Managed Extensions; error: new syntax
```

[ok] とに含まれる値は、`rslt`整数値に暗黙的に変換されます。 Visual C では、この呼び出しはコンパイルに失敗します。 正常に変換してを変換演算子を挿入する必要があります。

```
f( safe_cast<int>( rslt )); // ok: new syntax
```

## <a name="the-scope-of-the-clr-enum-type"></a>CLR 列挙型のスコープ

C および C++ 言語の変更点の 1 つが、C++ では、構造体の施設内のスコープを追加します。 C では、構造体は、インターフェイスまたは関連付けられているスコープのいずれかのサポートがない場合は集計データだけです。 これは非常に根本的な変更時に、C 言語から多くの新しい C++ ユーザーの間で論争が。 ネイティブと CLR 列挙型間のリレーションシップは似ています。

マネージ拡張で、試行をネイティブ列挙型内のスコープがない場合をシミュレートするために CLR 列挙型の列挙子の弱く挿入された名前を定義しました。 これは失敗に終わりました。 問題は、こうすると、列挙子に流出グローバル名前空間、名前の衝突の管理が困難になります。 新しい構文で CLR 列挙型内のスコープをサポートしている他の CLR 言語に準拠の対象がいます。

これは、修飾せずに、CLR 列挙型の列挙子の使用が新しい構文で認識されないことを意味します。 実際の例を見てみましょう。

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

列挙子の名前を使用して、3 つの非修飾 (`(1)`、 `(2)`、および`(3)`) を順番にソース コードをコンパイルする新しい構文の変換で修飾する必要があります。 元のソース コードの正しい変換を次に示します。

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

これは、ネイティブと CLR 列挙型の設計戦略を変更します。 Visual C では、関連付けられているスコープを維持、CLR enum は、クラス内で列挙型の宣言をカプセル化する効果的なも必要になります。 この手法進化ベル研究所でそれは cfront 2.0 の前後にもグローバル名前の汚染の問題を解決するためにします。

Jerry Schwarz ベル研究所によって新しい iostream ライブラリの元のベータ版リリース、Jerry がカプセル化しないライブラリ、およびなどの一般的な列挙子に対して定義されているすべての関連付けられた列挙`read`、 `write`、`append`など、ユーザーは、既存のコードをコンパイルするはほぼ不可能です。 など、名前に手を加える 1 つのソリューションがあった`io_read`、`io_write`など。、列挙型のスコープを追加して、言語を変更する 2 つ目のソリューションがあったことがこの実用的時にします。 中間ソリューションが、クラス内で列挙型をカプセル化、またはクラス階層では、タグ名と列挙型の列挙子の両方が、それを囲むクラス スコープを設定する場所です。)少なくとも最初は、クラス内で列挙型の配置に関する動機は、哲学的ながありませんが、グローバル名前空間の汚染の問題を実際の応答。

Visual C 列挙型では不要になったクラス内で列挙型をカプセル化することに説得力のある利点です。 実際には、表示している場合、`System`名前空間には、その列挙型、クラス、および同じ宣言領域に位置付けられますインターフェイスのすべてが表示されます。

## <a name="see-also"></a>関連項目

[値型とその動作 (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[列挙型クラス](../windows/enum-class-cpp-component-extensions.md)