---
description: '詳細情報: Array および WriteOnlyArray (C++/CX)'
title: Array と WriteOnlyArray (C++/CX)
ms.date: 01/22/2017
ms.assetid: ef7cc5f9-cae6-4636-8220-f789e5b6aea4
ms.openlocfilehash: 4c4f9415f401f1180786608288e33691c82fbdfa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302791"
---
# <a name="array-and-writeonlyarray-ccx"></a>Array と WriteOnlyArray (C++/CX)

通常の C スタイル配列または [`std::array`](../standard-library/array-class-stl.md) C++/cx プログラムで自由に使用できますが ( [`std::vector`](../standard-library/vector-class.md) 多くの場合、より適しています)、メタデータに公開されている API では、C スタイルの配列またはベクターを、 [`Platform::Array`](../cppcx/platform-array-class.md) [`Platform::WriteOnlyArray`](../cppcx/platform-writeonlyarray-class.md) 使用方法に応じてまたは型に変換する必要があります。 [`Platform::Array`](../cppcx/platform-array-class.md)型は効率的でも強力でもありません [`std::vector`](../standard-library/vector-class.md) 。そのため、一般的なガイドラインとして、配列要素で多くの操作を実行する内部コードでの使用を避ける必要があります。

次の配列型は、ABI を介して渡すことができます。

1. `const Platform::Array^`

1. `Platform::Array^*`

1. `Platform::WriteOnlyArray`

1. 戻り値 `Platform::Array^`

これらの配列型は、Windows ランタイムによって定義される3種類の配列パターンを実装するために使用します。

PassArray
呼び出し元が、配列をメソッドに渡すときに使用します。 C++ 入力パラメーターの型はです **`const`** [`Platform::Array`](../cppcx/platform-array-class.md) \<T> 。

FillArray
呼び出し元が、メソッドが入力する配列を渡すときに使用します。 C++ 入力パラメーターの型はです [`Platform::WriteOnlyArray`](../cppcx/platform-writeonlyarray-class.md) \<T> 。

ReceiveArray
呼び出し元が、メソッドが割り当てる配列を受け取るときに使用します。 C++/CX では、配列を Array^ として戻り値で返すことも、型 Array^* として Out パラメーターとして返すこともできます。

## <a name="passarray-pattern"></a>PassArray パターン

クライアントコードが配列を C++ メソッドに渡し、メソッドがその配列を変更しない場合、メソッドは配列をとして受け入れ `const Array^` ます。 Windows ランタイムアプリケーションバイナリインターフェイス (ABI) レベルでは、これを " *Pass array*" と呼びます。 次の例は、JavaScript に割り当てられた配列を、読み取り側の C++ 関数に渡す方法を示しています。

[!code-javascript[cx_arrays#101](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_1.js)]

次のスニペットは、C++ メソッドを示します。

[!code-cpp[cx_arrays#01](../cppcx/codesnippet/CPP/js-array/class1.cpp#01)]

## <a name="receivearray-pattern"></a>ReceiveArray パターン

*Receivearray* パターンでは、クライアントコードは配列を宣言し、それをメモリを割り当てて初期化するメソッドに渡します。 C++ 入力パラメーターの型は、hat へのポインターです `Array<T>^*` 。 次の例は、JavaScript で配列オブジェクトを宣言し、それを、メモリを割り当て、要素を初期化して JavaScript に返す C++ 関数に渡す方法を示しています。 JavaScript は、割り当てられた配列を戻り値として扱いますが、C++ 関数は出力パラメーターとして扱います。

[!code-javascript[cx_arrays#102](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_3.js)]

次のスニペットは、C++ メソッドを実装する 2 通りの方法を示します。

[!code-cpp[cx_arrays#02](../cppcx/codesnippet/CPP/js-array/class1.cpp#02)]

## <a name="fill-arrays"></a>Fill 配列

配列を呼び出し元で割り当て、呼び出し先で初期化または変更する場合は、 `WriteOnlyArray`を使用します。 次の例は、 `WriteOnlyArray` を使用する C++ 関数を実装して、JavaScript から呼び出す方法を示しています。

[!code-javascript[cx_arrays#103](../cppcx/codesnippet/JavaScript/array-and-writeonlyarray-c-_5.js)]

次のスニペットは、C++ メソッドを実装する方法を示します。

[!code-cpp[cx_arrays#03](../cppcx/codesnippet/CPP/js-array/class1.cpp#03)]

## <a name="array-conversions"></a>配列変換

この例では、を使用して [`Platform::Array`](../cppcx/platform-array-class.md) 他の種類のコレクションを構築する方法を示します。

[!code-cpp[cx_arrays#05](../cppcx/codesnippet/CPP/js-array/class1.cpp#05)]

次の例では、 [`Platform::Array`](../cppcx/platform-array-class.md) C スタイル配列からを構築し、パブリックメソッドから返す方法を示します。

[!code-cpp[cx_arrays#06](../cppcx/codesnippet/CPP/js-array/class1.cpp#06)]

## <a name="jagged-arrays"></a>ジャグ配列

Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていないため、パブリック メソッドで `IVector<Platform::Array<T>>` を戻り値またはメソッド パラメーターとして使用することはできません。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、 `IVector<IVector<T>^>`を使用します。

## <a name="use-arrayreference-to-avoid-copying-data"></a>ArrayReference 使用による、データ コピーの回避

データが ABI を介してに渡されていて、 [`Platform::Array`](../cppcx/platform-array-class.md) 最終的にはそのデータを C スタイル配列で処理して効率を上げる場合は、 [Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) を使用して余分なコピー操作を回避することができます。 を [`Platform::ArrayReference`](../cppcx/platform-arrayreference-class.md) 受け取るパラメーターに引数としてを渡すと、は `Platform::Array` 、指定した `ArrayReference` C スタイル配列にデータを直接格納します。 `ArrayReference` にソース データへのロック オンがないため、呼び出しが完了する前に別のスレッドでそのデータが変更されるかまたは削除された場合、結果は不確定になることに注意してください。

次のコードスニペットは、操作の結果をにコピーする方法 [`DataReader`](/uwp/api/windows.storage.streams.datareader) `Platform::Array` (通常のパターン) と、を代わりにデータを `ArrayReference` C スタイル配列に直接コピーする方法を示しています。

[!code-cpp[cx_arrays#07](../cppcx/codesnippet/CPP/js-array/class1.h#07)]

## <a name="avoid-exposing-an-array-as-a-property"></a>配列をプロパティとして公開することを回避する方法

一般に、ref クラスで `Platform::Array` 型をプロパティとして公開することは避ける必要があります。これは、クライアント コードが単一要素にアクセスしようとしている場合でも、配列全体が返されるためです。 パブリック ref クラスでシーケンスコンテナーをプロパティとして公開する必要がある場合は、を使用することを [`Windows::Foundation::IVector`](/uwp/api/windows.foundation.collections.ivector-1) お勧めします。 プライベートまたは内部 Api (メタデータには発行されません) では、などの標準 C++ コンテナーの使用を検討してください [`std::vector`](../standard-library/vector-class.md) 。

## <a name="see-also"></a>関連項目

[型システム](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間のリファレンス](../cppcx/namespaces-reference-c-cx.md)
