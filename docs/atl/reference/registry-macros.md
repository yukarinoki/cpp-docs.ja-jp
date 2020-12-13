---
description: 詳細については、「レジストリマクロ」を参照してください。
title: レジストリマクロ
ms.date: 08/19/2019
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
ms.openlocfilehash: e1f85e43f64dd34455cb9ec453ab3719b07f67f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138888"
---
# <a name="registry-macros"></a>レジストリマクロ

これらのマクロは、役に立つタイプライブラリとレジストリ機能を定義します。

|名前|説明|
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL.DLL への依存を回避するために、オブジェクトの登録コードをオブジェクトに含めることを指定します。|
|[DECLARE_LIBID](#declare_libid)|ATL がタイプライブラリの *libid* を取得する方法を提供します。|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|既定の ATL 登録を回避します。|
|[DECLARE_REGISTRY](#declare_registry)|システムレジストリ内のメインオブジェクトのエントリを入力または削除します。|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|*Appid* を自動的に登録するために必要な情報を指定します。|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|名前付きリソースを検索し、その中でレジストリスクリプトを実行します。|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|ID 番号で識別されたリソースを検索し、その中でレジストリスクリプトを実行します。|

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="_atl_static_registry"></a><a name="_atl_static_registry"></a> _ATL_STATIC_REGISTRY

ATL.DLL に対する依存関係を避けるために、オブジェクトの登録コードをオブジェクトに含める必要があることを示すシンボル。

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>解説

ATL_STATIC_REGISTRY を定義する場合は、次のコードを使用する必要があります。

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

## <a name="declare_libid"></a><a name="declare_libid"></a> DECLARE_LIBID

ATL がタイプライブラリの *libid* を取得する方法を提供します。

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>パラメーター

*libid*<br/>
タイプ ライブラリの GUID。

### <a name="remarks"></a>解説

派生クラスで DECLARE_LIBID を使用 `CAtlModuleT` します。

### <a name="example"></a>例

属性が設定されていないウィザードで生成された ATL プロジェクトには、このマクロの使用例が含まれています。

## <a name="declare_no_registry"></a><a name="declare_no_registry"></a> DECLARE_NO_REGISTRY

このマクロが表示されるクラスに対して既定の ATL 登録を行わないようにする場合は、DECLARE_NO_REGISTRY を使用します。

```
DECLARE_NO_REGISTRY()
```

## <a name="declare_registry"></a><a name="declare_registry"></a> DECLARE_REGISTRY

標準クラスの登録をシステムレジストリに入力するか、システムレジストリから削除します。

```
DECLARE_REGISTRY(
    class,
    pid,
    vpid,
    nid,
    flags )
```

### <a name="parameters"></a>パラメーター

*class*<br/>
から旧バージョンとの互換性のために用意されています。

*pid*<br/>
からバージョン固有のプログラム識別子である LPCTSTR。

*vpid*<br/>
からバージョンに依存しないプログラム識別子である LPCTSTR。

*nid*<br/>
からプログラムの説明として使用するレジストリ内のリソース文字列のインデックスである UINT。

*flags*<br/>
からレジストリ内のプログラムのスレッド処理モデルを含む DWORD。 THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG のいずれかの値である必要があります。

### <a name="remarks"></a>解説

標準登録は、CLSID、プログラム ID、バージョンに依存しないプログラム ID、説明文字列、およびスレッドモデルで構成されています。

ATL クラス追加ウィザードを使用してオブジェクトまたはコントロールを作成すると、ウィザードによってスクリプトベースのレジストリサポートが自動的に実装され、ファイルに [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) マクロが追加されます。 スクリプトベースのレジストリがサポートされないようにするには、このマクロを DECLARE_REGISTRY に置き換える必要があります。 DECLARE_REGISTRY は、上記で説明した5つの基本キーのみをレジストリに挿入します。 他のキーをレジストリに挿入するには、手動でコードを記述する必要があります。

## <a name="declare_registry_appid_resourceid"></a><a name="declare_registry_appid_resourceid"></a> DECLARE_REGISTRY_APPID_RESOURCEID

*Appid* を自動的に登録するために必要な情報を指定します。

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>パラメーター

*resid*<br/>
*Appid* に関する情報を格納する .rgs ファイルのリソース id。

*appid*<br/>
GUID。

### <a name="remarks"></a>解説

派生クラスで DECLARE_REGISTRY_APPID_RESOURCEID を使用 `CAtlModuleT` します。

### <a name="example"></a>例

クラスコードの追加ウィザードを使用して ATL プロジェクトに追加されたクラスには、このマクロの使用例が含まれています。

## <a name="declare_registry_resource"></a><a name="declare_registry_resource"></a> DECLARE_REGISTRY_RESOURCE

レジストリファイルを格納している名前付きリソースを取得し、スクリプトを実行してオブジェクトをシステムレジストリに入力するか、システムレジストリから削除します。

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からリソースの文字列識別子。

### <a name="remarks"></a>解説

ATL プロジェクトウィザードを使用してオブジェクトまたはコントロールを作成すると、ウィザードによってスクリプトベースのレジストリサポートが自動的に実装され、DECLARE_REGISTRY_RESOURCE に似た [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) マクロがファイルに追加されます。

最適化されたレジストリアクセスを行うために、ATL レジストリコンポーネント (レジストラー) と静的にリンクすることができます。 レジストラーコードに静的にリンクするには、次の行を *.pch* ファイル (Visual Studio 2017 以前の *stdafx.h* ) に追加します。

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

実行時に ATL で置換値を置換する場合は、DECLARE_REGISTRY_RESOURCE または DECLARE_REGISTRY_RESOURCEID マクロを指定しないでください。 代わりに、構造体の配列を作成し `_ATL_REGMAP_ENTRIES` ます。各エントリには、実行時にプレースホルダーを置き換える値と組み合わせた変数プレースホルダーが含まれています。 次に、 [CAtlModule:: UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) または [CAtlModule:: UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources)を呼び出して、配列を渡します。 これにより、構造体のすべての置換値が `_ATL_REGMAP_ENTRIES` レジストラーの置換マップに追加されます。

置換可能なパラメーターとスクリプトの詳細については、「 [ATL レジストリコンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)」を参照してください。

## <a name="declare_registry_resourceid"></a><a name="declare_registry_resourceid"></a> DECLARE_REGISTRY_RESOURCEID

[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)と同じですが、ウィザードで生成された UINT を使用して、文字列名ではなくリソースを識別する点が異なります。

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からウィザードで生成されたリソースの識別子。

### <a name="remarks"></a>解説

ATL プロジェクトウィザードを使用してオブジェクトまたはコントロールを作成すると、ウィザードによってスクリプトベースのレジストリサポートが自動的に実装され、ファイルに DECLARE_REGISTRY_RESOURCEID マクロが追加されます。

最適化されたレジストリアクセスを行うために、ATL レジストリコンポーネント (レジストラー) と静的にリンクすることができます。 レジストラーコードに静的にリンクするには、 *stdafx.h* ファイル (Visual Studio 2019 以降では *.pch* ) に次の行を追加します。

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

実行時に ATL で置換値を置換する場合は、DECLARE_REGISTRY_RESOURCE または DECLARE_REGISTRY_RESOURCEID マクロを指定しないでください。 代わりに、構造体の配列を作成し `_ATL_REGMAP_ENTRIES` ます。各エントリには、実行時にプレースホルダーを置き換える値と組み合わせた変数プレースホルダーが含まれています。 次に、 [CAtlModule:: UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) または [CAtlModule:: UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources)を呼び出して、配列を渡します。 これにより、構造体のすべての置換値が `_ATL_REGMAP_ENTRIES` レジストラーの置換マップに追加されます。

置換可能なパラメーターとスクリプトの詳細については、「 [ATL レジストリコンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)」を参照してください。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
