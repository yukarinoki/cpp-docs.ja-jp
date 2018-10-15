---
title: 配列 (C +/cli および C++/cli CX) |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b1a1f977e15d80d631799d8a9e101a8c85e3aaf1
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328104"
---
# <a name="arrays-ccli-and-ccx"></a>配列 (C +/cli および C++/cli CX)

`Platform::Array<T>` C++ 型/cli CX、または**配列**キーワードは c++/cli CLI では、指定した型と初期値の配列を宣言します。

## <a name="all-platforms"></a>すべてのプラットフォーム

右山かっこ (>) で宣言した後、オブジェクトのハンドル (^) 修飾子を使用して配列を宣言する必要があります。
型の一部でない配列の要素の数。 1 つの配列変数は、さまざまなサイズの配列を参照できます。

標準の C++ とは異なり、添字演算子はポインターの算術演算のシノニムではなく、可換的ではありません。

配列の詳細についてを参照してください。

- [方法: C++/CLI で配列を使用する](../dotnet/how-to-use-arrays-in-cpp-cli.md)

- [可変個引数リスト (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)

## <a name="windows-runtime"></a>Windows ランタイム

配列のメンバーである、`Platform`名前空間。 配列には、1 次元のみ指定できます。

### <a name="syntax"></a>構文

構文の最初の例では、 **ref 新しい**配列を割り当てる集計キーワード。 2 番目の例では、ローカル配列を宣言します。

```cpp
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]

[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}
```

*修飾子*<br/>
(省略可能)1 つ以上のこれらのストレージ クラス指定子:[変更可能な](../cpp/mutable-data-members-cpp.md)、[揮発性](../cpp/volatile-cpp.md)、 [const](../cpp/const-cpp.md)、 [extern](../cpp/using-extern-to-specify-linkage.md)、[静的](../cpp/static-members-cpp.md).

*配列型*<br/>
配列変数の型。 有効な種類は Windows ランタイム クラスと基本型、ref クラスと構造体、値クラスと構造体、およびネイティブ ポインター (`type*`)。

*rank*<br/>
(省略可能)配列の次元の数。 1 にする必要があります。

*identifier*<br/>
配列変数の名前。

*初期化の種類*<br/>
配列を初期化する値の型。 通常、*配列型*と*初期化型*は同じ型。 ただし、型が異なる可能性への変換がある場合*初期化型*に*配列型*— たとえば場合、*初期化型*から派生*配列型*します。

*初期化リスト*<br/>
(省略可能)配列の要素の初期化は中かっこ内の値のコンマ区切りの一覧。 たとえば場合、*ランクのサイズ-一覧*された`(3)`、3 つの要素の 1 次元配列を宣言しています*初期化リスト*可能性があります`{1,2,3}`。

### <a name="remarks"></a>Remarks

型がで参照カウントの配列であるかどうかをコンパイル時に検出できます`__is_ref_array(type)`します。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

### <a name="examples"></a>使用例

次の例では、100 個の要素のある 1 次元配列を作成します。

```cpp
// cwr_array.cpp
// compile with: /ZW
using namespace Platform;
ref class MyClass {};
int main() {
   // one-dimensional array
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);
   My1DArray[99] = ref new MyClass();
}
```

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="syntax"></a>構文

構文の最初の例では、 **gcnew**配列を割り当てるキーワード。 2 番目の例では、ローカル配列を宣言します。

```cpp
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]

[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier = 
    {initialization-list [,...]}
```

*修飾子*<br/>
(省略可能)1 つ以上のこれらのストレージ クラス指定子:[変更可能な](../cpp/mutable-data-members-cpp.md)、[揮発性](../cpp/volatile-cpp.md)、 [const](../cpp/const-cpp.md)、 [extern](../cpp/using-extern-to-specify-linkage.md)、[静的](../cpp/static-members-cpp.md).

*配列型*<br/>
配列変数の型。 有効な種類は Windows ランタイム クラスと基本型、ref クラスと構造体、値クラスと構造体は、ネイティブ ポインター (`type*`)、およびネイティブ POD (plain old データ) の型。

*rank*<br/>
(省略可能)配列の次元の数。 既定値は 1 になります。最大値は、32 です。 配列の各次元では配列自体です。

*identifier*<br/>
配列変数の名前。

*初期化の種類*<br/>
配列を初期化する値の型。 通常、*配列型*と*初期化型*は同じ型。 ただし、型が異なる可能性への変換がある場合*初期化型*に*配列型*— たとえば場合、*初期化型*から派生*配列型*します。

*ランクのサイズの一覧*<br/>
配列の各次元のサイズのコンマ区切りの一覧。 また場合、*初期化リスト*パラメーターを指定すると、コンパイラは、各次元のサイズを推測できると*ランクのサイズの一覧*を省略できます。

*初期化リスト*<br/>
(省略可能)配列の要素の初期化は中かっこ内の値のコンマ区切りの一覧。 コンマ区切りのリストが入れ子になったまたは*初期化リスト*多次元配列内の要素を初期化する項目。

たとえば場合、*ランクのサイズ-一覧*された`(3)`、3 つの要素の 1 次元配列を宣言しています*初期化リスト*可能性があります`{1,2,3}`。 場合*ランクのサイズ-一覧*された`(3,2,4)`、最初の次元、2 番目の場合、2 つの要素および第 3 回目、4 つの要素の 3 つの要素の 3 次元の配列を宣言する*初期化リスト*可能性があります`{{1,2,3},{0,0},{-5,10,-21,99}}`)。

### <a name="remarks"></a>Remarks

**配列**では、[プラットフォーム、既定では、および cli 名前空間](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)名前空間。

標準の C++ のような配列のインデックスは 0 から始まる、および角かっこ () を使用して配列が添字です。 標準の C++ とは異なり、多次元配列のインデックスは、一連の各ディメンションの角かっこ ([) 演算子ではなく、各次元のインデックスの一覧で指定されます。 たとえば、*識別子*[*index1*、 *index2*] の代わりに*識別子*[*index1*] [ *index2*]。

継承するすべてのマネージ配列`System::Array`します。 任意のメソッドまたはプロパティの`System::Array`配列変数に直接適用できます。

ポインターは、配列を割り当てするときに要素型のマネージ クラスでは、要素が 0 に初期化します。

値の型には、配列の割り当てするときに要素型を持つ`V`の既定のコンス トラクター`V`配列の各要素に適用されます。 詳細については、次を参照してください。 [C++ ネイティブ型に対応する .NET Framework (C +/cli CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)します。

コンパイル時に、型、共通言語ランタイム (CLR) 配列では、かどうかを検出できます`__is_ref_array(type)`します。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

次の例を 100 個の要素を持つ 1 次元配列の最初の次元の 3 つの要素、5 の 2 番目の要素と 3 番目の 6 つの要素を持つ 3 次元の配列を作成します。

```cpp
// clr_array.cpp
// compile with: /clr
ref class MyClass {};
int main() {
   // one-dimensional array
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);
   My1DArray[99] = gcnew MyClass();

   // three-dimensional array
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);
   My3DArray[0,0,0] = gcnew MyClass();
}
```

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)