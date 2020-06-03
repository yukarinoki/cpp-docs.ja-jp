---
title: オブジェクト マップ マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 66a418019ba506a5832c8e3ad86a3764c1186df0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326211"
---
# <a name="object-map-macros"></a>オブジェクト マップ マクロ

これらのマクロは、オブジェクト マップとエントリを定義します。

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|オブジェクト マップに入力されるクラス オブジェクトのテキストの説明を指定できます。|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|ATL オブジェクトをオブジェクト マップに入力し、レジストリを更新して、オブジェクトのインスタンスを作成します。|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|オブジェクトを登録して初期化するように指定する一方で、`CoCreateInstance` を使用してオブジェクトを外部で作成できないように指定できます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="declare_object_description"></a><a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION

クラス オブジェクトのテキストの説明を指定できます。

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]クラス オブジェクトの説明。

### <a name="remarks"></a>解説

ATL は[、OBJECT_ENTRY_AUTO](#object_entry_auto)マクロを通じて、この説明をオブジェクト マップに入力します。

DECLARE_OBJECT_DESCRIPTION関数を`GetObjectDescription`実装します。 [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription)

関数`GetObjectDescription`は によって呼`IComponentRegistrar::GetComponents`び出されます。 `IComponentRegistrar`は、DLL 内の個々のコンポーネントを登録および登録解除できるオートメーション インターフェイスです。 ATL プロジェクト ウィザードを使用してコンポーネント レジストラー オブジェクトを作成すると、ウィザードによって自動的`IComponentRegistrar`にインターフェイスが実装されます。 `IComponentRegistrar`は通常、マイクロソフトのトランザクション サーバーによって使用されます。

ATL プロジェクト ウィザードの詳細については、ATL[プロジェクトの作成に関する記事を](../../atl/reference/creating-an-atl-project.md)参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

## <a name="object_entry_auto"></a><a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO

ATL オブジェクトをオブジェクト マップに入力し、レジストリを更新して、オブジェクトのインスタンスを作成します。

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
[in]クラス*という*C++ クラスによって実装される COM クラスの CLSID。

*class*<br/>
[in]*clsid*で表される COM クラスを実装する C++ クラスの名前。

### <a name="remarks"></a>解説

オブジェクトのエントリ マクロは、クラスの登録、初期化、および作成をサポートするためにプロジェクトのグローバル スコープに配置されます。

OBJECT_ENTRY_AUTO、このオブジェクトのクリエータクラスおよびクラスファクトリクリエータクラス`CreateInstance`関数の関数ポインタを、自動生成された ATL オブジェクト マップに入力します。 [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)が呼び出されると、オブジェクト マップ内の各オブジェクトのシステム レジストリが更新されます。

次の表は、オブジェクト マップに追加された情報を、このマクロの 2 番目のパラメーターとして指定されたクラスから取得する方法を示しています。

|の情報|から得た|
|---------------------|-------------------|
|COM 登録|[レジストリ マクロ](../../atl/reference/registry-macros.md)|
|クラスファクトリの作成|[クラス ファクトリ マクロ](../../atl/reference/aggregation-and-class-factory-macros.md)|
|インスタンスの作成|[集計マクロ](../../atl/reference/aggregation-and-class-factory-macros.md)|
|コンポーネント カテゴリ登録|[カテゴリ マクロ](../../atl/reference/category-macros.md)|
|クラスレベルの初期化とクリーンアップ|[オブジェクトメイン](ccomobjectrootex-class.md#objectmain)|

## <a name="object_entry_non_createable_ex_auto"></a><a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

オブジェクトを登録して初期化するように指定する一方で、`CoCreateInstance` を使用してオブジェクトを外部で作成できないように指定できます。

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
[in]クラス*という*C++ クラスによって実装される COM クラスの CLSID。

*class*<br/>
[in]*clsid*で表される COM クラスを実装する C++ クラスの名前。

### <a name="remarks"></a>解説

オブジェクトのエントリ マクロは、クラスの登録、初期化、および作成をサポートするためにプロジェクトのグローバル スコープに配置されます。

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTOを使用すると、オブジェクトの登録と初期化を指定できますが (詳細については[OBJECT_ENTRY_AUTO](#object_entry_auto)参照)、オブジェクトは を使用して`CoCreateInstance`作成できません。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
