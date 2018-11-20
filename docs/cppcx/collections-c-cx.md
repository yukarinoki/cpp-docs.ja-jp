---
title: コレクション (C++/CX)
ms.date: 11/19/2018
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
ms.openlocfilehash: d256e333ddf31bdb637680b70718af85e753a21d
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176394"
---
# <a name="collections-ccx"></a>コレクション (C++/CX)

C +/cli/CX プログラムの場合は、標準テンプレート ライブラリ (STL) コンテナー、または他のユーザー定義コレクション型を自由に使用を行うことができます。 ただし、コレクションを渡す場合、双方向 Windows ランタイム アプリケーション バイナリ インターフェイス (ABI) を越えて — たとえば、XAML コントロールまたは JavaScript クライアント: Windows ランタイムのコレクション型を使用する必要があります。

Windows ランタイムは、コレクションと関連する型、および C + 用のインターフェイスを定義します。/cli CX は collection.h ヘッダー ファイルで具象 C++ 実装を提供します。 この図は、コレクション型間のリレーションシップを示しています。

![C&#43;&#43;&#47;/CX 継承ツリーのコレクション型](../cppcx/media/cppcxcollectionsinheritancetree.png "C&#43;&#43;&#47;/CX 継承ツリーのコレクション型")

- [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md) は [std::vector クラス](../standard-library/vector-class.md)と似ています。

- [Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md) は [std::map class クラス](../standard-library/map-class.md)と似ています。

- [Platform::Collections::VectorView クラス](../cppcx/platform-collections-vectorview-class.md) と[Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md) は `Vector` と `Map`の読み取り専用のバージョンです。

- 反復子は [Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md)で定義されます。 これらの反復子は、STL 反復子の要件を満たし、任意の [Windows::Foundation::Collections](../standard-library/algorithm-functions.md#find)インターフェイス型や  [Platform::Collections](../standard-library/algorithm-functions.md#count_if)具象型で [std::find](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.aspx) 、 [std::count_if](../cppcx/platform-collections-namespace.md) などの STL アルゴリズムを使えるようにします。 たとえば、c# で作成され、STL アルゴリズムを適用する Windows ランタイム コンポーネントのコレクションを反復処理することができますこれを意味します。

   > [!IMPORTANT]
   > プロキシ反復子 `VectorIterator` と `VectorViewIterator` は、プロキシ オブジェクト `VectoryProxy<T>` と `ArrowProxy<T>` を利用して、STL コンテナーでの使用を有効にします。 詳細については、この記事で後述する「VectorProxy 要素」を参照してください。

- C++/cli CX コレクション型と同じスレッド セーフの保証を STL コンテナーがサポートされます。

- [Windows::Foundation::Collections::IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) と [Windows::Foundation::Collections::IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) は、コレクションがさまざまな方法で変更されるときに発生するイベントを定義します。 これらのインターフェイスを実装すると、  [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) と [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) は、XAML コレクションとのデータ バインドをサポートします。 たとえば、 `Vector` にデータ バインドされている `Grid`がある場合、コレクションに項目を追加すると、変更がグリッド UI に反映されます。

## <a name="vector-usage"></a>ベクターの使用

クラス、シーケンス コンテナーを別の Windows ランタイム コンポーネントに渡すときに使用[:foundation:: IVector\<T >](https://msdn.microsoft.com/library/windows/apps/br206631.aspx)パラメーターまたは戻り値の型として、[プラットフォーム。Collections::Vector\<T >](../cppcx/platform-collections-vector-class.md)具象実装として。 パブリックの戻り値またはパラメーターで `Vector` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 このエラーは、 `Vector` を `IVector`に変更することで解決できます。

> [!IMPORTANT]
> 独自のプログラム内のシーケンスを渡している場合は、 `Vector` か `std::vector` のどちらかを使用します。それらの方が `IVector`より効率的であるためです。 ABI を介してコンテナーを渡す場合にのみ、 `IVector` を使用します。
>
> Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていませんし、そのため、IVector を渡すことはできません < platform::array\<T >> を戻り値またはメソッド パラメーターとして。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、 `IVector<IVector<T>^>`を使用します。

`Vector<T>` は、コレクションでの項目の追加、削除、およびアクセスに必要なメソッドを提供します。暗黙的に `IVector<T>`に変換可能です。 `Vector<T>`のインスタンスで STL アルゴリズム使用することもできます。 次の例は、基本的な使用法をいくつか示しています。 [begin 関数](../cppcx/begin-function.md) と [end 関数](../cppcx/end-function.md) は `Platform::Collections` 名前空間のもので、 `std` 名前空間のものではありません。

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

使用する既存のコードがある場合`std::vector`Windows ランタイム コンポーネントで再利用のいずれかを使用して、`Vector`を受け取るコンス トラクター、`std::vector`または構築する反復子のペアを`Vector`時点を渡すことで、ABI を介してコレクションです。 次の例は、 `Vector` からの効率的な初期化のために `std::vector`移動コンストラクターを使用する方法を示しています。 移動操作の後、元の `vec` 変数は有効でなくなります。

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

今後のいつか、ABI を介して渡す必要がある文字列ベクターがある場合、その文字列を最初に `std::wstring` 型として作成するのかそれとも `Platform::String^` 型として作成するのかを決定する必要があります。 その文字列に対して多くの処理を実行する必要がある場合、 `wstring`を使用します。 それ以外の場合は、文字列を `Platform::String^` 型として作成して、後で変換するコストを回避してください。 また、これらの文字列を `std:vector` と `Platform::Collections::Vector` のどちらに内部的に埋め込むのかも決定する必要があります。 一般に、 `std::vector` を使用し、ABI を介してコンテナーを渡す場合にのみ、そこから `Platform::Vector` を作成します。

## <a name="value-types-in-vector"></a>ベクターにおける値の型

[Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) に格納される要素は、暗黙的にまたは指定したカスタム [std::equal_to](../standard-library/equal-to-struct.md) 比較子を使用するかして、等値比較をサポートする必要があります。 すべての参照型とすべてのスカラー型は、暗黙的に等値比較をサポートしています。 [Windows::Foundation::DateTime](https://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)などの非スカラー値型の場合や、カスタム比較 ( `objA->UniqueID == objB->UniqueID`など) の場合、カスタム関数オブジェクトを提供する必要があります。

## <a name="vectorproxy-elements"></a>VectorProxy 要素

[Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)と[Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)の使用を有効にする`range for`ループとなどのアルゴリズム[std::sort](../standard-library/algorithm-functions.md#sort) で[IVector\<T >](https://msdn.microsoft.com/library/windows/apps/br206631.aspx)コンテナー。 ただし、C++ ポインターの逆参照を使って `IVector` 要素にアクセスすることはできません。これらの要素には、 [GetAt](https://msdn.microsoft.com/library/windows/apps/br206634.aspx) メソッドと [SetAt](https://msdn.microsoft.com/library/windows/apps/br206642.aspx) メソッドを使ってアクセスすることしかできません。 そのため、これらの反復子を使用して、プロキシ クラス`Platform::Details::VectorProxy<T>`と`Platform::Details::ArrowProxy<T>`を介して個々 の要素へのアクセスを提供する__\*__、 __->__、および__\[]__ 演算子は、標準ライブラリで必要とします。 厳密には、 `IVector<Person^> vec`が指定されている場合、 `*begin(vec)` の型は `VectorProxy<Person^>`になります。 ただし、プロキシ オブジェクトは、ほとんどの場合、コードに対して透過的です。 これらのプロキシ オブジェクトは反復子によって内部でのみ使用されるため文書化されませんが、その機構の動作がわかっていると便利です。

`range for` コンテナーに対して `IVector` ループを使用する場合は、 `auto&&` を使用して反復子変数が `VectorProxy` 要素に正しくバインドされるようにします。 `auto` または `auto&`を使用すると、コンパイラ警告 C4239 が発生し、警告テキストに `VectoryProxy` が示されます。

`range for` に対する `IVector<Person^>`ループ処理の例を次に示します。 実行が 64 行のブレークポイントで停止していることに注意してください。 **[クイック ウォッチ]** ウィンドウには、反復子変数 `p` が実際には `VectorProxy<Person^>` メンバー変数と `m_v` メンバー変数を持つ `m_i` であることが示されています。 ただし、この変数で `GetType` を呼び出すと、 `Person` インスタンス `p2`と同一の型が返されます。 `VectorProxy` と `ArrowProxy` が **[クイック ウォッチ]**、デバッガーの一部のコンパイラ エラー、またはその他の場所に表示される場合でも、通常はそれらについて明示的にコーディングする必要はありません。

![範囲内にある VectorProxy&#45;基づく for ループ](../cppcx/media/vectorproxy-1.png "範囲内にある VectorProxy&#45;基づく for ループ")

プロキシ オブジェクトに関してコーディングする必要があるのは、 `dynamic_cast` 要素コレクションで特定の型の XAML オブジェクトを探している場合など、要素で `UIElement` を実行する必要がある場合です。 この場合は、最初に [Platform::Object](../cppcx/platform-object-class.md)^ に要素をキャストし、その後に動的キャストを実行する必要があります。

```cpp
void FindButton(UIElementCollection^ col)
{
    // Use auto&& to avoid warning C4239
    for (auto&& elem : col)
    {
        Button^ temp = dynamic_cast<Button^>(static_cast<Object^>(elem));
        if (nullptr != temp)
        {
            // Use temp...
        }
    }
}
```

## <a name="map-usage"></a>マップの使用

この例は、項目の挿入し、で確認する方法を示します、 [:map](../cppcx/platform-collections-map-class.md)、戻って、`Map`読み取り専用 [Windows::Foundation::Collections::IMapView] として/uwp api/Windows.Foundation.Collections.IMapView_K_V_) の型。

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

一般に、内部マップ機能については、パフォーマンス上の理由で `std::map` 型を優先します。 ABI を介してコンテナーを渡す必要がある場合は、 [std::map](../cppcx/platform-collections-map-class.md) から [Platform::Collections::Map](../standard-library/map-class.md) を構築し、 `Map` を [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)として返します。 パブリックの戻り値またはパラメーターで `Map` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 このエラーは、 `Map` を `IMap`に変更することで解決できます。 たとえば、実行するルックアップや挿入の数が多くなく、ABI を介して頻繁にコレクションを渡すなどの場合、最初から `Platform::Collections::Map` を使用し `std::map`を変換するコストを回避した方がコストを抑えられることがあります。 どちらの場合も、 `IMap` のルックアップ操作と挿入操作は、3 つの種類で最もパフォーマンスが低いので避けます。 ABI を介してコンテナーを渡すポイントでのみ、 `IMap` に変換します。

## <a name="value-types-in-map"></a>マップにおける値の型

[Platform::Collections::Map](../cppcx/platform-collections-map-class.md) 内の要素は、順序付きです。 `Map` に格納しようとする要素は、厳密な弱い順序付けに基づき、"より小さい" 比較をサポートする必要があります。このために、暗黙的な比較、または開発者が指定したカスタム比較子 [stl::less](../standard-library/less-struct.md) が使用されます。 スカラー型では、この比較を暗黙的にサポートしています。 `Windows::Foundation::DateTime`などの非スカラー値型、またはカスタム比較 ( `objA->UniqueID < objB->UniqueID`など) の場合、カスタム比較子を提供する必要があります。

## <a name="collection-types"></a>コレクション型

コレクションは、シーケンス コレクションと関連コレクションそれぞれの変更可能バージョンと読み取り専用バージョンという 4 つのカテゴリに分類されます。 さらに、C +/cli CX はコレクションのアクセスを簡略化する 3 つの反復子クラスを提供することでコレクションを拡張します。

変更可能なコレクションの要素は変更できますが、 *ビュー*と呼ばれる読み取り専用コレクションの要素は読み取りしか実行できません。 要素を[platform::collections:](../cppcx/platform-collections-vector-class.md)または[Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) 、反復子またはコレクションを使用してコレクションにアクセスできる[vector::getat](../cppcx/platform-collections-vector-class.md#getat)とインデックス。 関連コレクションの要素のコレクションを使用してアクセスできる[map::lookup](../cppcx/platform-collections-map-class.md#lookup)とキー。

[Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)<br/>
変更可能な関連コレクション。 マップ要素は、キーと値のペアです。 キーを検索してその関連付けられた値を取得することと、キーと値のペアをすべて繰り返すことの両方がサポートされています。

`Map` と `MapView` は、 `<K, V, C = std::less<K>>`で template 宣言されるので、比較子をカスタマイズできます。  さらに、 `Vector` と `VectorView` は `<T, E = std::equal_to<T>>` で template 宣言されるので、 `IndexOf()`の動作をカスタマイズできます。 これは、値の構造体の `Vector` と `VectorView` について特に重要です。 たとえば、ベクターを作成する\<::datetime > を DateTime オーバー ロードしていないため、カスタム比較子を提供する必要があります、演算子 = =。

[Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)<br/>
`Map`の読み取り専用バージョン。

[Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)<br/>
変更可能なシーケンス コレクション。 `Vector<T>` は、定数時間ランダム アクセス操作と償却定数時間の [追加](../cppcx/platform-collections-vector-class.md#append) 操作をサポートしています。

[Platform::Collections::VectorView クラス](../cppcx/platform-collections-vectorview-class.md)<br/>
`Vector`の読み取り専用バージョン。

[Platform::Collections::InputIterator クラス](../cppcx/platform-collections-inputiterator-class.md)<br/>
STL 入力反復子の要件を満たす STL の反復子。

[Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)<br/>
変更可能な STL ランダム アクセス反復子の要件を満たす STL 反復子。

[Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
STL の  `const` ランダム アクセス反復子の要件を満たす STL 反復子。

### <a name="begin-and-end-functions"></a>begin() および end() 関数

処理する STL の使用を簡略化`Vector`、 `VectorView`、 `Map`、 `MapView`、および任意`Windows::Foundation::Collections`オブジェクト、C +/cli CX のオーバー ロードをサポートしている、 [begin 関数](../cppcx/begin-function.md)と[終了関数](../cppcx/end-function.md)非メンバー関数。

次の表は、使用できる反復子と関数の一覧を示しています。

|Iterators|関数|
|---------------|---------------|
|[Platform::Collections::VectorIterator\<T >](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (内部に格納[:foundation:: IVector\<T >](https://msdn.microsoft.com/library/windows/apps/br206631.aspx)と int です)。|[begin](../cppcx/begin-function.md)/ [end](../cppcx/end-function.md)([Windows::Foundation::Collections:: IVector\<T>](https://msdn.microsoft.com/library/windows/apps/br206631.aspx))|
|[Platform::Collections::VectorViewIterator\<T >](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (内部に格納[IVectorView\<T >](https://msdn.microsoft.com/library/windows/apps/br226058.aspx)^ と int です)。|[開始](../cppcx/begin-function.md)/ [エンド](../cppcx/end-function.md)([IVectorView\<T >](https://msdn.microsoft.com/library/windows/apps/br226058.aspx)^)|
|[Platform::Collections::InputIterator\<T >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (内部に格納[IIterator\<T >](https://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ および T)|[開始](../cppcx/begin-function.md)/ [エンド](../cppcx/end-function.md)([IIterable\<T >](https://msdn.microsoft.com/library/windows/apps/br226024.aspx))|
|[Platform::Collections::InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (内部に格納[IIterator\<T >](https://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ および T)|[開始](../cppcx/begin-function.md)/ [エンド](../cppcx/end-function.md)([IMap\<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)します。|
|[Platform::Collections::InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (内部に格納[IIterator\<T >](https://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ および T)|[開始](../cppcx/begin-function.md)/ [エンド](../cppcx/end-function.md)([Windows:: Foundation::Collections::IMapView]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_))|

### <a name="collection-change-events"></a>コレクション変更イベント

`Vector` と `Map` は、XAML コレクションでのデータ バインドをサポートしていますが、これは、コレクション オブジェクトが変更またはリセットされたとき、またはコレクションのいずれかの要素が挿入、削除、または変更されたときに発生するイベントを実装することで実現されています。 データ バインドをサポートする独自の型を作成できます。ただし、 `Map` と `Vector` から継承することはできません。これらの型はシールされているためです。

[Windows::Foundation::Collections::VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler) デリゲートと [Windows::Foundation::Collections::MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler) デリゲートは、コレクション変更イベントのイベント ハンドラーのシグネチャを指定します。 [Windows::Foundation::Collections::CollectionChange](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx) パブリック列挙型クラス、 `Platform::Collection::Details::MapChangedEventArgs` 、 `Platform::Collections::Details::VectorChangedEventArgs` ref クラスは、イベントの原因を特定するためにイベント引数を格納します。 `*EventArgs`で型が定義されている、`Details`名前空間を作成または使用するときに明示的に使用する必要がないため`Map`または`Vector`します。

## <a name="see-also"></a>関連項目

[型システム](../cppcx/type-system-c-cx.md)<br/>
[Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間参照](../cppcx/namespaces-reference-c-cx.md)