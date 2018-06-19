---
title: ATL コピー ポリシー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34b9ed5dca45633a5ab980d38b8a7cda151f5dc7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358528"
---
# <a name="atl-copy-policy-classes"></a>ATL コピー ポリシー クラス
ポリシー クラスのコピーは[ユーティリティ クラス](../atl/utility-classes.md)初期化するために、コピー、および使用データを削除します。 ポリシー クラスのコピーでは、任意の種類、データのコピーのセマンティクスを定義し、別のデータ型の間で変換を定義することができます。  
  
 次のテンプレートの実装では、使用してコピーのポリシー クラス ATL:  
  
-   [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)  
  
-   [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)  
  
-   [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)  
  
 コピーまたはテンプレートの引数として渡すことができるコピー ポリシー クラスのデータの変換に必要な情報をカプセル化してこれらのクラスの極端な再利用性の ATL 開発者が用意されています。 たとえば、任意の任意のデータ型を使用して、コレクションを実装する必要がある場合を提供する必要があります、ポリシーの適切なコピーです。コレクションを実装するコードをタッチすることはありませんがあります。  
  
## <a name="definition"></a>定義  
 定義上、次の静的関数を提供するクラスはコピー ポリシー クラスです。  
  
 `static void init(` `DestinationType` `* p);`  
  
 `static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`  
  
 `static void destroy(` `DestinationType` `* p);`  
  
 型を置き換えることができます`DestinationType`と*SourceType*コピー ポリシーごとに任意のデータ型。  
  
> [!NOTE]
>  ATL コードでクラスの使用はいる任意のデータ型のコピー ポリシー クラスを定義できますが、意味のある型を制限する必要があります。 たとえば、コピー ポリシーを使用して class ATL のコレクションと列挙子の実装、 `DestinationType` COM インターフェイスのメソッドのパラメーターとして使用できる型である必要があります。  
  
 使用して**init** 、データを初期化するために**コピー** 、データをコピーして**破棄**データを解放します。 初期化の正確な意味、コピー、および破棄は、コピー ポリシー クラスのドメインを関連するデータ型によって異なります。  
  
 使用法とコピー ポリシー クラスの実装で次の 2 つの要件があります。  
  
-   最初のパラメーター**コピー**のみを使用して初期化されたデータへのポインターを受信する必要があります**init**です。  
  
-   **破棄**を使用して初期化されたデータへのポインターを受け取る必要がありますだけ**init**または経由でコピーした**コピー**です。  
  
## <a name="standard-implementations"></a>標準の実装  
 ATL の形式で 2 つのコピー ポリシー クラスには、 **_Copy**と **_CopyInterface**テンプレート クラス。  
  
-   **_Copy**クラスにより、コピーのみ同種 (データ型の間で変換ではない) 両方を指定する 1 つのテンプレート パラメーターのみ提供していますので`DestinationType`と*SourceType*です。 このテンプレートの汎用実装が初期化または破棄のコードを含まず、使用して`memcpy`データをコピーします。 ATL は、の特殊化も用意されています。 **_Copy**の**バリアント**、 `LPOLESTR`、 **OLEVERB**、および**CONNECTDATA**データ型。  
  
-   **_CopyInterface**クラスが標準の COM 規則に従うインターフェイス ポインターをコピーするための実装を提供します。 もう一度このクラスは、同種のコピーのみ、単純な代入とへの呼び出しを使うよう`AddRef`コピーを実行します。  
  
## <a name="custom-implementations"></a>カスタムの実装  
 通常、異機種混在 (つまり、データ型間の変換) をコピーするための独自のコピー ポリシー クラスを定義する必要があります。 カスタム コピー ポリシー クラスの例については、ファイルを見る、VCUE_Copy.h およびで VCUE_CopyString.h、 [ATLCollections](../visual-cpp-samples.md)サンプルです。 これらのファイルには、2 つのテンプレートのコピー ポリシー クラスが含まれて`GenericCopy`と`MapCopy`の特殊化の数と`GenericCopy`データ型が異なるためです。  
  
### <a name="genericcopy"></a>GenericCopy  
 `GenericCopy` 指定することができます、 *SourceType*と`DestinationType`テンプレート引数として。 ここでは、最も一般的な形式の`GenericCopy`VCUE_Copy.h からクラス。  
  
 [!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]  
  
 VCUE_Copy.h には、このクラスの次の特殊化も含まれています: `GenericCopy<BSTR>`、 `GenericCopy<VARIANT, BSTR>`、`GenericCopy<BSTR, VARIANT>`です。 VCUE_CopyString.h にはからコピーするための特殊化が含まれています**std::string**%s: `GenericCopy<std::string>`、 `GenericCopy<VARIANT, std::string>`、および`GenericCopy<BSTR, std::string>`です。 強化でした`GenericCopy`さらに、独自の特殊化を提供することによりします。  
  
### <a name="mapcopy"></a>MapCopy  
 `MapCopy` マップ データを格納し、変換先の入力の種類を指定することができますので、C++ 標準ライブラリ型マップにコピーするデータが格納されたと仮定します。 クラスの実装のみによって提供される typedef を使用する、 *MapType*クラスをソース データの種類を決定し、適切な呼び出しを`GenericCopy`クラスです。 このクラスの特殊化は必要ありません。  
  
 [!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリに基づくコレクションを実装します。](../atl/implementing-an-stl-based-collection.md)   
 [ATLCollections サンプル](../visual-cpp-samples.md)

