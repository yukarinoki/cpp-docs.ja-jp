---
title: 型システム (C++/CX)
ms.date: 02/03/2017
ms.assetid: b67bee8a-b526-4872-969e-ef22724e88fe
ms.openlocfilehash: fbc7a178621624e396c80509703ce1b5b4c19162
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745955"
---
# <a name="type-system-ccx"></a>型システム (C++/CX)

Windows ランタイムのアーキテクチャを使用すると、使用することが C + + CX、Visual Basic、Visual c# および JavaScript を直接 Windows API にアクセスし、その他の Windows ランタイム アプリおよびコンポーネントと相互運用するアプリやコンポーネントを記述します。 C++ で記述されているユニバーサル Windows プラットフォーム アプリは、CPU で直接実行するネイティブ コードにコンパイルします。 C# または Visual Basic で記述されているユニバーサル Windows プラットフォーム アプリでは、Microsoft intermediate language (MSIL) にコンパイルし、共通言語ランタイム (CLR) で実行します。 JavaScript で記述されているユニバーサル Windows プラットフォーム アプリでは、実行時環境で実行します。 Windows ランタイムのオペレーティング システム コンポーネント自体は C++ で記述し、ネイティブ コードとして実行します。 これらのコンポーネントとユニバーサル Windows プラットフォーム アプリのすべては、Windows ランタイム アプリケーション バイナリ インターフェイス (ABI) を介して直接通信します。

最新の C++ 表現での Windows ランタイムのサポートを有効にするのには、Microsoft が作成された C + + CX します。 C + + CX 組み込み基本型と C++ アプリと他の言語で記述されたアプリが ABI 間で通信するコンポーネントを有効にする基本的な Windows ランタイム型の実装を提供します。 任意の Windows ランタイム型を使用したり、クラス、構造体、インターフェイス、およびその他のユニバーサル Windows プラットフォーム アプリおよびコンポーネントで使用できるその他のユーザー定義型を作成できます。 C + で記述されたユニバーサル Windows プラットフォーム アプリ/cli CX できますもを使用して、通常の C++ クラスと構造体のパブリック アクセシビリティがあるない限り、します。

C++/CX 言語プロジェクションと内部動作の詳しい説明については、次のブログ記事を参照してください。

1. [C + +/CX Part 0 of \[n\]:概要](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction)

1. [C + +/CX Part 1 of \[n\]:単純なクラス](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class)

1. [C + +/CX Part 2 of \[n\]:ハット記号が型](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats)

1. [C + +/CX Part 3 of \[n\]:工事中](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)

1. [C + +/CX Part 4 of \[n\]:静的メンバー関数](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions)

## <a name="windows-metadata-winmd-files"></a>Windows メタデータ (.winmd) ファイル

C++ で記述されたユニバーサル Windows プラットフォーム アプリをコンパイルするときに、コンパイラがネイティブのマシン語コードの実行可能ファイルが生成され。、パブリックの Windows ランタイム型の説明を含む別の Windows メタデータ (.winmd) ファイルも生成されます。これは、クラス、構造体、列挙体、インターフェイス、パラメーター化されたインターフェイス、およびデリゲートが含まれます。 メタデータの形式は、.NET Framework アセンブリで使用される形式に似ています。  C++ コンポーネントでは、.winmd ファイルにはメタデータのみ含まれています。実行可能コードは、別個のファイルに存在します。 これは、Windows に含まれている Windows ランタイム コンポーネントの場合です。 WinMD ファイルの名前はソース コードのルート名前空間のプレフィックスに一致またはそれ自体である必要があります。 (.NET Framework 言語の場合、.winmd ファイルには、.NET Framework アセンブリのようにコードとメタデータの両方が含まれます。)

.winmd ファイルのメタデータは、コードの公開されたサーフェイスを表します。 公開された型が他のユニバーサル Windows プラットフォームに表示される言語にかかわらず、他のアプリはで記述します。 したがって、メタデータ、または発行されたコードが、この Windows ランタイムの型システムによって指定された型を含めることできますのみ。 標準クラス、配列、テンプレートまたは STL コンテナーなど、C++ 固有の言語構造体は、メタデータで発行できません。理由は、JavaScript または C# クライアント アプリケーションが対処できないからです。

型またはメソッドがメタデータに表示されるかどうかは、適用されるアクセシビリティ修飾子によって異なります。 型を表示するには、型が名前空間で宣言され、パブリックとして宣言されている必要があります。 非パブリックの ref クラスは、コード内で内部ヘルパー型として許可されています。これは、メタデータでは表示されません。 パブリック ref クラスでも、すべてのメンバーが表示されるとは限りません。 次の表では、パブリック ref クラスでの C++ アクセス指定子と Windows ランタイム メタデータの可視性の関係を示します。

|||
|-|-|
|**メタデータで公開**|**メタデータで非公開**|
|public|private|
|protected|internal|
|public protected|private protected|

.winmd ファイルの内容を表示するために、 **オブジェクト ブラウザー** を使用できます。 Windows に含まれている Windows ランタイム コンポーネントは、Windows.winmd ファイル内でです。 Default.winmd ファイルには、C + で使用される基本的な型が含まれています。/cli/CX、および platform.winmd Platform 名前空間からのその他の種類が含まれています。 既定では、ユニバーサル Windows プラットフォーム アプリのすべての C++ プロジェクトで、これら 3 つの .winmd ファイルが含まれます。

> [!TIP]
> [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md) 型は、パブリックではないので、.winmd ファイルには表示されません。 これらは、 `Windows::Foundation::Collections`で定義されているインターフェイスのプライベート C++ 固有の実装です。 JavaScript または c# で記述された Windows ランタイム アプリが不明な[platform::collections: クラス](../cppcx/platform-collections-vector-class.md)は、使用できるが、 `Windows::Foundation::Collections::IVector`。 `Platform::Collections` 型は、collection.h で定義されます。

## <a name="windows-runtime-type-system-in-ccx"></a>Windows ランタイム型システムの C + + CX

次のセクションでは、Windows ランタイムの型システムと c++ のサポートについての主要な機能を説明する/cli CX します。

### <a name="namespaces"></a>名前空間

名前空間内ですべての Windows ランタイム型を宣言する必要があります。Windows API 自体は、名前空間で構成されています。 .winmd ファイルには、ルート名前空間と同じ名前が必要です。 たとえば、A.B.C.MyClass という名前のクラスは、A.winmd または A.B.winmd または A.B.C.winmd という名前のメタデータ ファイルで定義されている場合のみインスタンス化できます。 DLL の名前が .winmd ファイル名と一致する必要はありません。

Windows API 自体が、名前空間ごとに構成された、十分にファクタリングされたクラス ライブラリとして再開発されました。  すべての Windows ランタイム コンポーネントは、Windows.* 名前空間で宣言されます。

詳細については、[名前空間と型の可視性](../cppcx/namespaces-and-type-visibility-c-cx.md)を参照してください。

### <a name="fundamental-types"></a>基本的な型

Windows ランタイムには、次の基本的な型、UInt8、Int16、UInt16、Int32、UInt32、Int64、UInt64、1 つ、Double、Char16、Boolean、および文字列を定義します。 C + + CX は、uint16、uint32、uint64、int16、int32、int64、float32、float64、および char16 として、既定の名前空間で基本的な数値型をサポートします。 ブール値と文字列も、Platform 名前空間で定義されます。

C +/cli CX は、uint8、等しくも定義されています。 `unsigned char`、Windows ランタイムでサポートされていないとパブリック Api では使用できません。

基本型を null 許容にするには、 [Platform::IBox インターフェイス](../cppcx/platform-ibox-interface.md) にラップします。 詳細については、「 [値クラスと構造体](../cppcx/value-classes-and-structs-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

基本型の詳細については、「 [基本型](../cppcx/fundamental-types-c-cx.md)

### <a name="strings"></a>文字列

Windows ランタイム文字列とは、16 ビット UNICODE 文字の不変のシーケンスです。 Windows ランタイムの文字列として投影`Platform::String^`します。 このクラスは、文字列の作成、操作、および `wchar_t`への変換 (およびその逆) のためのメソッドを提供します。

詳細については、「 [文字列](../cppcx/strings-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="arrays"></a>配列

Windows ランタイムでは、任意の型の 1 次元の配列をサポートします。 配列の配列はサポートされていません。  C++/cli CX、Windows ランタイムの配列として投影されます、 [platform::array クラス](../cppcx/platform-array-class.md)します。

詳細については、次を参照してください[Array と WriteOnlyArray。](../cppcx/array-and-writeonlyarray-c-cx.md)

### <a name="ref-classes-and-structs"></a>Ref クラスと構造体

Windows ランタイム クラスが投影される C +/cli CX ref クラスまたは ref 構造体として、参照でコピーされるためです。 ref クラスと ref 構造体のメモリ管理は、参照カウントによって透過的に処理されます。 オブジェクトへの最後の参照がスコープ外に出ると、オブジェクトは破棄されます。 ref クラスまたは ref 構造体では、次のことができます。

- コンストラクター、メソッド、プロパティ、およびイベントをメンバーとして格納できます。 これらのメンバーには、パブリック、プライベート、プロテクト、または内部のアクセシビリティを指定できます。

- プライベートの入れ子になった構造体、列挙体、またはクラス定義を格納できます。

- 1 つの基底クラスから直接継承し、任意の数のインターフェイスを実装できます。 ref クラスは、いずれも [Platform::Object Class](../cppcx/platform-object-class.md) に暗黙的に変換可能で、 [Object::ToString](../cppcx/platform-object-class.md#tostring)などの仮想メソッドをオーバーライドできます。

パブリック コンストラクターを持つ ref クラスは、さらに派生されることを防ぐために、シール済みとして宣言する必要があります。

詳細については、「 [Ref クラスと構造体](../cppcx/ref-classes-and-structs-c-cx.md)

### <a name="value-classes-and-structs"></a>値クラスと構造体

値クラスまたは値の構造体は、基本的なデータ構造体を表し、フィールドのみ格納できます。フィールドには、値クラス、値構造体、または `Platform::String^`型が含まれます。  値構造体と値クラスは、値によってコピーされます。

値構造体を null 許容にするには、IBox インターフェイスにラップします。

詳細については、「 [値クラスと構造体](../cppcx/value-classes-and-structs-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="partial-classes"></a>部分クラス

部分クラスの機能を使用して、1 つのクラスを複数のファイルに対して定義できます。 この機能は主に、XAML エディターなどのコード生成ツールで、編集するファイルにアクセスせずに 1 つのファイルを変更するために使用されます。

詳細については、「 [部分クラス](../cppcx/partial-classes-c-cx.md)

### <a name="properties"></a>プロパティ

プロパティは、任意の Windows ランタイム型のパブリック データ メンバーであるし、取得/設定メソッドのペアとして実装されます。 クライアント コードは、パブリック フィールドのようにプロパティにアクセスします。 カスタムの get または set コードを必要とするプロパティは、 *trivial プロパティ* と呼ばれ、明示的な get または set メソッドを使用せずに宣言できます。

詳細については、「 [プロパティ](../cppcx/properties-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="windows-runtime-collections-in-ccx"></a>C++ Windows ランタイム コレクション/cli CX

Windows ランタイムでは、各言語が独自の方法で実装するコレクション型のインターフェイスのセットを定義します。 C +/cli CX 実装を提供します、 [platform::collections: クラス](../cppcx/platform-collections-vector-class.md)、 [::map クラス](../cppcx/platform-collections-map-class.md)、および他の関連する具象コレクション型と互換性がある、標準テンプレート ライブラリ (STL) の対応します。

詳細については、[コレクション](../cppcx/collections-c-cx.md)を参照してください。

### <a name="template-ref-classes"></a>テンプレート ref クラス

プライベート ref クラスおよび内部 ref クラスは、テンプレート化および特化できます。

詳細については、「 [テンプレート ref クラス](../cppcx/template-ref-classes-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="interfaces"></a>インターフェイス

Windows ランタイム インターフェイスは、パブリック プロパティ、メソッド、および ref クラスまたは ref 構造体は、インターフェイスから継承している場合に実装する必要がありますイベントのセットを定義します。

詳細については、「[インターフェイス](../cppcx/interfaces-c-cx.md)」を参照してください。

### <a name="enums"></a>列挙体

列挙体クラスは、Windows ランタイムでは、C++ では、スコープ列挙型に似ています。 基になる型は int32 です。[Flags] 属性が適用された場合、基になる型は uint32 です。

詳細については、「 [列挙体](../cppcx/enums-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="delegates"></a>デリゲート

Windows ランタイムでは、デリゲートは、C++ の std::function オブジェクトに似ています。 これは、互換性のあるシグニチャを持つクライアント提供関数を呼び出すために使用される、特殊な種類の ref クラスです。  デリゲートは、イベントの種類として、Windows ランタイムで最もよく使用されます。

詳細については、「[デリゲート](../cppcx/delegates-c-cx.md)」を参照してください。

### <a name="exceptions"></a>例外

C++/CX では、カスタムの例外の種類、 [std::exception](../standard-library/exception-class.md) 型、および [Platform::Exception](../cppcx/platform-exception-class.md) 型をキャッチできます。

詳細については、「 [例外](../cppcx/exceptions-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="events"></a>イベント

イベントは、型がデリゲート型の、ref クラスまたは ref 構造体のパブリック メンバーです。 イベントに対して可能なのは、所有するクラスによる呼び出し (つまり、発生) だけです。 ただし、クライアント コードが独自の関数を提供することはできます。それらの関数はイベント ハンドラーと呼ばれ、所有クラスでイベントが発生したときに呼び出されます。

詳細については、「 [イベント](../cppcx/events-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="casting"></a>キャスト

C++/CX は、標準 C++ のキャスト演算子 [static_cast](../cpp/static-cast-operator.md)、 [dynamic_cast](../cpp/dynamic-cast-operator.md)、および [reinterpret_cast](../cpp/reinterpret-cast-operator.md)をサポートし、C++/CX に固有の **safe_cast** 演算子もサポートします。

詳細については、「 [キャスト](../cppcx/casting-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="boxing"></a>ボックス化

ボックス化された変数は、参照セマンティクスが必要な場合に参照型にラップされる値の型です。

詳細については、「 [ボックス化](../cppcx/boxing-c-cx.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

### <a name="attributes"></a>属性

属性は、任意の Windows ランタイム型または型のメンバーに適用することができますし、実行時に検査できるメタデータ値です。 Windows ランタイムの一般的な属性のセットを定義する、`Windows::Foundation::Metadata`名前空間。 このリリースでは、パブリック インターフェイスでユーザー定義の属性は Windows ランタイムによってサポートされていません。

## <a name="api-deprecation"></a>API の非推奨

パブリック Api を Windows ランタイム システムの種類で使用される同じ属性を使用して非推奨としてマークする方法について説明します。

詳細については、[型とメンバーを非推奨化](../cppcx/deprecating-types-and-members-c-cx.md)を参照してください。

## <a name="see-also"></a>関連項目

[Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)
