---
title: ATL コピー ポリシー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: f40f31124d4547076249a7459ac4b63cc25305d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317390"
---
# <a name="atl-copy-policy-classes"></a>ATL コピー ポリシー クラス

コピー・ポリシー・クラスは、データの初期化、コピー、および削除に使用される[ユーティリティー・クラス](../atl/utility-classes.md)です。 コピー ポリシー クラスを使用すると、任意のデータ型のコピー セマンティクスを定義し、異なるデータ型間の変換を定義できます。

ATL は、次のテンプレートの実装でコピー ポリシー クラスを使用します。

- [コマヌビプル](../atl/reference/ccomenumimpl-class.md)

- [イエヌオンストルプル](../atl/reference/ienumonstlimpl-class.md)

- [コレクションオンストルプル](../atl/reference/icollectiononstlimpl-class.md)

テンプレート引数として渡すことができるコピー ポリシー クラスのデータのコピーまたは変換に必要な情報をカプセル化することで、ATL 開発者はこれらのクラスを極端に再利用できるようにしました。 たとえば、任意のデータ型を使用してコレクションを実装する必要がある場合、適切なコピー ポリシーを指定するだけで済みます。コレクションを実装するコードに触れる必要はありません。

## <a name="definition"></a>定義

定義上、次の静的関数を提供するクラスは、コピー ポリシー クラスです。

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

型`DestinationType`と*SourceType*を、各コピー ポリシーの任意のデータ型に置き換えることができます。

> [!NOTE]
> 任意のデータ型に対してコピー ポリシー クラスを定義できますが、ATL コードでクラスを使用すると、意味のある型が制限されます。 たとえば、ATL のコレクションまたは列挙子の実装でコピー ポリシー クラスを使用`DestinationType`する場合は、COM インターフェイス メソッドのパラメーターとして使用できる型である必要があります。

**init**を使用して、データの初期化、**データ**のコピー、データの解放を**行う破棄**を行います。 初期化、コピー、および破棄の正確な意味は、コピー ポリシー クラスのドメインであり、関連するデータ型によって異なります。

コピー ポリシー クラスの使用と実装には、次の 2 つの要件があります。

- **コピー**する最初のパラメータは **、init**を使用して初期化したデータへのポインタのみを受け取る必要があります。

- **destroy**は **、init**を使用して初期化したデータまたは**copy**を使用してコピーしたデータへのポインタを受け取る必要があります。

## <a name="standard-implementations"></a>標準実装

ATL は、テンプレート クラスと`_Copy``_CopyInterface`テンプレート クラスの形式で 2 つのコピー ポリシー クラスを提供します。

- この`_Copy`クラスでは、同種のコピーのみを許可します (データ型間の変換はできません) は、テンプレート パラメーター`DestinationType`を 1 つだけ提供して、両方と*SourceType*を指定するだけです。 このテンプレートの汎用実装には、初期化コードや破棄コードが含`memcpy`まれず、データのコピーに使用されます。 ATL は、バリアント型、LPOLESTR 型、OLEVERB 型、および CONNECTDATA データ型の`_Copy`特殊化も提供します。

- この`_CopyInterface`クラスは、標準 COM 規則に従ってインターフェイス ポインターをコピーするための実装を提供します。 このクラスは同種のコピーのみを許可するため、単純な代入と呼び出しを`AddRef`使用してコピーを実行します。

## <a name="custom-implementations"></a>カスタム実装

通常、異種コピー (つまり、データ型間の変換) 用に独自のコピー ポリシー クラスを定義する必要があります。 カスタム コピー ポリシー クラスの例については[、ATLCollections](../overview/visual-cpp-samples.md)サンプルの VCUE_Copy.h と VCUE_CopyString.h のファイルを参照してください。 これらのファイルには、2 つのテンプレート`GenericCopy`コピー`MapCopy`ポリシー クラスと、 に加`GenericCopy`えて、さまざまなデータ型に対する特殊化が含まれています。

### <a name="genericcopy"></a>ジェネリックコピー

`GenericCopy`を使用して、*ソースの種類*と`DestinationType`テンプレートの引数として指定できます。 VCUE_Copy.h のクラスの最も`GenericCopy`一般的な形式は次のとおりです。

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy.h には、このクラスの次の特殊な情報`GenericCopy<BSTR>`も`GenericCopy<VARIANT, BSTR>`含`GenericCopy<BSTR, VARIANT>`まれています。 VCUE_CopyString.h には **、std::string** `GenericCopy<std::string>`s: 、、`GenericCopy<VARIANT, std::string>`および からコピー`GenericCopy<BSTR, std::string>`するための特殊な機能が含まれています。 あなた自身の`GenericCopy`さらなる専門化を提供することによって、あなたは強化することができます。

### <a name="mapcopy"></a>マップコピー

`MapCopy`コピーされるデータは C++ 標準ライブラリスタイルのマップに格納されていると仮定するため、データが格納されるマップの種類とコピー先の型を指定できます。 クラスの実装では *、MapType*クラスによって提供される typedef を使用して、ソース データの型を決定し、適切`GenericCopy`なクラスを呼び出すだけです。 このクラスの特殊化は必要ありません。

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ ベースのコレクションの実装](../atl/implementing-an-stl-based-collection.md)<br/>
[ATL コレクションのサンプル](../overview/visual-cpp-samples.md)
