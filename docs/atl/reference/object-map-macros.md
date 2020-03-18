---
title: オブジェクトマップマクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 73dc924527bac8499adefab3d0d6b51afa500a5a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423022"
---
# <a name="object-map-macros"></a>オブジェクトマップマクロ

これらのマクロは、オブジェクトマップとエントリを定義します。

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|オブジェクトマップに入力される、クラスオブジェクトのテキストの説明を指定できます。|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|ATL オブジェクトをオブジェクトマップに入力し、レジストリを更新して、オブジェクトのインスタンスを作成します。|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|オブジェクトを登録して初期化するように指定する一方で、`CoCreateInstance` を使用してオブジェクトを外部で作成できないように指定できます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION

クラスオブジェクトの説明テキストを指定できます。

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からクラスオブジェクトの説明。

### <a name="remarks"></a>解説

ATL は、この説明を[OBJECT_ENTRY_AUTO](#object_entry_auto)マクロを使用してオブジェクトマップに入力します。

DECLARE_OBJECT_DESCRIPTION は、 [CComCoClass:: GetObjectDescription](ccomcoclass-class.md#getobjectdescription)メソッドをオーバーライドするために使用できる `GetObjectDescription` 関数を実装します。

`GetObjectDescription` 関数は `IComponentRegistrar::GetComponents`によって呼び出されます。 `IComponentRegistrar` は、DLL 内の個々のコンポーネントを登録および登録解除できるオートメーションインターフェイスです。 ATL プロジェクトウィザードを使用してコンポーネントレジストラーオブジェクトを作成すると、ウィザードによって `IComponentRegistrar` インターフェイスが自動的に実装されます。 `IComponentRegistrar` は、通常、Microsoft Transaction Server によって使用されます。

ATL プロジェクトウィザードの詳細については、「 [Atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

##  <a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO

ATL オブジェクトをオブジェクトマップに入力し、レジストリを更新して、オブジェクトのインスタンスを作成します。

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
から*クラスの名前付き*クラスによって実装C++されている COM クラスの CLSID。

*class*<br/>
からClsid によってC++表される COM クラスを実装する*clsid*クラスの名前。

### <a name="remarks"></a>解説

オブジェクトのエントリ マクロは、クラスの登録、初期化、および作成をサポートするためにプロジェクトのグローバル スコープに配置されます。

OBJECT_ENTRY_AUTO は、このオブジェクトの creator クラスとクラスファクトリ creator `CreateInstance` クラスの関数ポインターを、自動生成された ATL オブジェクトマップに入力します。 [CAtlComModule:: RegisterServer](catlcommodule-class.md#registerserver)が呼び出されると、オブジェクトマップ内の各オブジェクトのシステムレジストリが更新されます。

次の表は、オブジェクトマップに追加された情報が、このマクロの2番目のパラメーターとして指定されたクラスから取得される方法を示しています。

|の情報|取得元|
|---------------------|-------------------|
|COM 登録|[レジストリに関するマクロ](../../atl/reference/registry-macros.md)|
|クラスファクトリの作成|[クラスファクトリマクロ](../../atl/reference/aggregation-and-class-factory-macros.md)|
|インスタンスの作成|[集計マクロ](../../atl/reference/aggregation-and-class-factory-macros.md)|
|コンポーネントカテゴリの登録|[カテゴリに関するマクロ](../../atl/reference/category-macros.md)|
|クラスレベルの初期化とクリーンアップ|[ObjectMain](ccomobjectrootex-class.md#objectmain)|

##  <a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

オブジェクトを登録して初期化するように指定する一方で、`CoCreateInstance` を使用してオブジェクトを外部で作成できないように指定できます。

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
から*クラスの名前付き*クラスによって実装C++されている COM クラスの CLSID。

*class*<br/>
からClsid によってC++表される COM クラスを実装する*clsid*クラスの名前。

### <a name="remarks"></a>解説

オブジェクトのエントリ マクロは、クラスの登録、初期化、および作成をサポートするためにプロジェクトのグローバル スコープに配置されます。

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO を使用すると、オブジェクトを登録して初期化する必要があることを指定できます (詳細については[OBJECT_ENTRY_AUTO](#object_entry_auto)を参照してください) が、`CoCreateInstance`で作成することはできません。

## <a name="see-also"></a>参照

[マクロ](../../atl/reference/atl-macros.md)
