---
description: '詳細情報: ATL コピーポリシークラス'
title: ATL コピーポリシークラス
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: 502befadbd9317602c49d9a5815dee6ebc239d78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165759"
---
# <a name="atl-copy-policy-classes"></a>ATL コピーポリシークラス

コピーポリシークラスは、データの初期化、コピー、および削除に使用される [ユーティリティクラス](../atl/utility-classes.md) です。 コピーポリシークラスを使用すると、あらゆる種類のデータのコピーセマンティクスを定義したり、異なるデータ型間の変換を定義したりすることができます。

ATL では、次のテンプレートの実装でコピーポリシークラスを使用します。

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)

- [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)

テンプレート引数として渡すことができるコピーポリシークラスのデータをコピーまたは変換するために必要な情報をカプセル化することによって、ATL 開発者はこれらのクラスを非常に再利用できるようになりました。 たとえば、任意のデータ型を使用してコレクションを実装する必要がある場合は、適切なコピーポリシーを指定するだけで済みます。コレクションを実装するコードを操作する必要はありません。

## <a name="definition"></a>定義

定義上、次の静的関数を提供するクラスは、コピーポリシークラスです。

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

これらの型 `DestinationType` と *SourceType* は、各コピーポリシーの任意のデータ型に置き換えることができます。

> [!NOTE]
> 任意のデータ型に対してコピーポリシークラスを定義できますが、ATL コードでクラスを使用すると、意味のある型を制限する必要があります。 たとえば、ATL のコレクションまたは列挙子の実装でコピーポリシークラスを使用する場合、は、 `DestinationType` COM インターフェイスメソッドのパラメーターとして使用できる型である必要があります。

**Init** を使用してデータを初期化し、**コピー** してデータをコピーし、**破棄** してデータを解放します。 初期化、コピー、および破棄の正確な意味は、コピーポリシークラスのドメインであり、関連するデータ型によって異なります。

コピーポリシークラスの使用と実装には、次の2つの要件があります。

- **コピー** する最初のパラメーターは、 **init** を使用して以前に初期化したデータへのポインターのみを受け取る必要があります。

- **破棄** では、前に **init** を使用して初期化したデータへのポインター、または **コピー** を使用してコピーしたデータへのポインターだけを受け取る必要があります。

## <a name="standard-implementations"></a>標準実装

ATL には、 `_Copy` テンプレートクラスとテンプレートクラスの2つのコピーポリシークラスが用意されてい `_CopyInterface` ます。

- `_Copy`クラスは `DestinationType` 、と *SourceType* の両方を指定する1つのテンプレートパラメーターのみを提供するため、同一のコピーのみを許可します (データ型間の変換はできません)。 このテンプレートの汎用実装には、初期化または破棄コードは含まれていません。を使用して `memcpy` データをコピーします。 ATL では、 `_Copy` VARIANT、LPOLESTR、OLEVERB、および CONNECTDATA データ型の特殊化も提供されています。

- クラスは、 `_CopyInterface` 標準の COM 規則に従ってインターフェイスポインターをコピーするための実装を提供します。 ここでも、このクラスでは、同一のコピーのみが許可されるため、単純な割り当てとの呼び出しを使用して `AddRef` コピーを実行します。

## <a name="custom-implementations"></a>カスタム実装

通常は、異種コピー (つまり、データ型間の変換) 用に独自のコピーポリシークラスを定義する必要があります。 カスタムコピーポリシークラスの例については、 [Atlcollections](../overview/visual-cpp-samples.md) サンプルのファイル VCUE_Copy を参照し VCUE_CopyString てください。 これらのファイルには、とという2つのテンプレートコピーポリシークラスが含まれ `GenericCopy` て `MapCopy` `GenericCopy` います。また、さまざまなデータ型のの特殊化がいくつかあります。

### <a name="genericcopy"></a>GenericCopy

`GenericCopy`*SourceType* と `DestinationType` as テンプレート引数を指定できます。 VCUE_Copy のクラスの最も一般的な形式を次に示します `GenericCopy` 。

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy には、このクラスの次のような特殊化も含まれています。 `GenericCopy<BSTR>` 、 `GenericCopy<VARIANT, BSTR>` 、 `GenericCopy<BSTR, VARIANT>` 。 VCUE_CopyString には、 **std:: string** s からコピーするための特殊化が含まれています: `GenericCopy<std::string>` 、 `GenericCopy<VARIANT, std::string>` 、および `GenericCopy<BSTR, std::string>` 。 独自の機能をさらに特殊化することで、を拡張でき `GenericCopy` ます。

### <a name="mapcopy"></a>MapCopy

`MapCopy` コピーされるデータは C++ 標準ライブラリスタイルのマップに格納されるため、データが格納されるマップの型と変換先の型を指定できます。 クラスの実装では、 *Maptype* クラスによって提供される typedef を使用して、ソースデータの型を判断し、適切なクラスを呼び出すだけ `GenericCopy` です。 このクラスの特殊化は必要ありません。

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>関連項目

[C++ 標準 Library-Based コレクションの実装](../atl/implementing-an-stl-based-collection.md)<br/>
[ATLCollections サンプル](../overview/visual-cpp-samples.md)
