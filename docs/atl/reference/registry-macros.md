---
title: レジストリ マクロ
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
ms.openlocfilehash: fd012b4300f4cd72cdc9ab363b770ac1dbefa06e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326038"
---
# <a name="registry-macros"></a>レジストリ マクロ

これらのマクロは、便利なタイプ ライブラリとレジストリ機能を定義します。

|||
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|オブジェクトの登録コードをオブジェクトに含めて ATL への依存を回避することを示します。Dll。|
|[DECLARE_LIBID](#declare_libid)|ATL がタイプ ライブラリの*libid*を取得する方法を提供します。|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|既定の ATL 登録を回避します。|
|[DECLARE_REGISTRY](#declare_registry)|システム レジストリ内のメイン オブジェクトのエントリを入力または削除します。|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|*appid*を自動的に登録するために必要な情報を指定します。|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|指定されたリソースを検索し、その中でレジストリ スクリプトを実行します。|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|ID 番号で識別されたリソースを検索し、その中でレジストリ スクリプトを実行します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="_atl_static_registry"></a><a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY

ATL への依存を回避するために、オブジェクトの登録コードをオブジェクトに含める必要があることを示す記号。Dll。

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>解説

ATL_STATIC_REGISTRYを定義する場合は、次のコードを使用する必要があります。

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

## <a name="declare_libid"></a><a name="declare_libid"></a>DECLARE_LIBID

ATL がタイプ ライブラリの*libid*を取得する方法を提供します。

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>パラメーター

*Libid*<br/>
タイプ ライブラリの GUID。

### <a name="remarks"></a>解説

派生クラスでDECLARE_LIBID`CAtlModuleT`を使用します。

### <a name="example"></a>例

属性のないウィザードで生成された ATL プロジェクトには、このマクロの使用例が表示されます。

## <a name="declare_no_registry"></a><a name="declare_no_registry"></a>DECLARE_NO_REGISTRY

このマクロが表示されるクラスに対する既定の ATL 登録を避ける場合は、DECLARE_NO_REGISTRYを使用します。

```
DECLARE_NO_REGISTRY()
```

## <a name="declare_registry"></a><a name="declare_registry"></a>DECLARE_REGISTRY

標準クラス登録をシステム レジストリに入力するか、システム レジストリから削除します。

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
[in]下位互換性のために含まれています。

*Pid*<br/>
[in]バージョン固有のプログラム ID である LPCTSTR。

*vpid*<br/>
[in]バージョン非依存プログラム ID である LPCTSTR。

*Nid*<br/>
[in]プログラムの説明として使用するレジストリ内のリソース文字列のインデックスである UINT。

*フラグ*<br/>
[in]レジストリ内のプログラムのスレッド モデルを含む DWORD。 値は、THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG のいずれかでなければなりません。

### <a name="remarks"></a>解説

標準登録は、CLSID、プログラム ID、バージョンに依存しないプログラム ID、記述ストリング、およびスレッド・モデルで構成されます。

ATL クラス追加ウィザードを使用してオブジェクトまたはコントロールを作成すると、ウィザードはスクリプト ベースのレジストリ サポートを自動的に実装し[、DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)マクロをファイルに追加します。 スクリプト ベースのレジストリ サポートを必要としない場合は、このマクロをDECLARE_REGISTRYに置き換える必要があります。 DECLARE_REGISTRYは、上記の 5 つの基本キーをレジストリに挿入するだけです。 他のキーをレジストリに挿入するコードは手動で記述する必要があります。

## <a name="declare_registry_appid_resourceid"></a><a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID

*appid*を自動的に登録するために必要な情報を指定します。

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>パラメーター

*レジンズ*<br/>
appid に関する情報を含む .rgs ファイルのリソース*ID。*

*Appid*<br/>
GUID。

### <a name="remarks"></a>解説

派生クラスでDECLARE_REGISTRY_APPID_RESOURCEID`CAtlModuleT`を使用します。

### <a name="example"></a>例

クラスの追加ウィザードを使用して ATL プロジェクトに追加されたクラスには、このマクロの使用例があります。

## <a name="declare_registry_resource"></a><a name="declare_registry_resource"></a>DECLARE_REGISTRY_RESOURCE

レジストリ ファイルを含む名前付きリソースを取得し、システム レジストリにオブジェクトを入力するか、またはシステム レジストリから削除するスクリプトを実行します。

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]リソースの文字列識別子。

### <a name="remarks"></a>解説

ATL プロジェクト ウィザードを使用してオブジェクトまたはコントロールを作成すると、ウィザードによってスクリプト ベースのレジストリ サポートが自動的に実装され、DECLARE_REGISTRY_RESOURCEに似た[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)マクロがファイルに追加されます。

ATL レジストリ コンポーネント (レジストラー) と静的にリンクして、最適化されたレジストリ アクセスを行うことができます。 レジストラー コードに静的にリンクするには、次の行を*pch.h*ファイル (Visual Studio 2017 以前の*stdafx.h)* に追加します。

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL で実行時に置換値を置換する場合は、DECLARE_REGISTRY_RESOURCEまたはDECLARE_REGISTRY_RESOURCEIDマクロを指定しないでください。 代わりに、構造体の`_ATL_REGMAP_ENTRIES`配列を作成し、各エントリには、実行時にプレースホルダーを置き換える値と組み合わせた変数のプレースホルダーが含まれています。 次[に、配列](catlmodule-class.md#updateregistryfromresourced)を渡して呼び出します。 [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources) これにより、構造体内のすべての置換値が`_ATL_REGMAP_ENTRIES`レジストラーの置換マップに追加されます。

置き換え可能なパラメータとスクリプトの詳細については[、「ATL レジストリ コンポーネント (レジストラー)」](../../atl/atl-registry-component-registrar.md)を参照してください。

## <a name="declare_registry_resourceid"></a><a name="declare_registry_resourceid"></a>DECLARE_REGISTRY_RESOURCEID

[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)と同じですが、ウィザードで生成された UINT を使用して、文字列名ではなくリソースを識別する点が異なります。

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]ウィザードで生成されたリソースの識別子。

### <a name="remarks"></a>解説

ATL プロジェクト ウィザードを使用してオブジェクトまたはコントロールを作成すると、ウィザードによってスクリプト ベースのレジストリ サポートが自動的に実装され、DECLARE_REGISTRY_RESOURCEID マクロがファイルに追加されます。

ATL レジストリ コンポーネント (レジストラー) と静的にリンクして、最適化されたレジストリ アクセスを行うことができます。 レジストラー コードに静的にリンクするには *、stdafx.h*ファイル (Visual Studio 2019 以降の*pch.h)* に次の行を追加します。

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL で実行時に置換値を置換する場合は、DECLARE_REGISTRY_RESOURCEまたはDECLARE_REGISTRY_RESOURCEIDマクロを指定しないでください。 代わりに、構造体の`_ATL_REGMAP_ENTRIES`配列を作成し、各エントリには、実行時にプレースホルダーを置き換える値と組み合わせた変数のプレースホルダーが含まれています。 次[に、配列](catlmodule-class.md#updateregistryfromresourced)を渡して呼び出します。 [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources) これにより、構造体内のすべての置換値が`_ATL_REGMAP_ENTRIES`レジストラーの置換マップに追加されます。

置き換え可能なパラメータとスクリプトの詳細については[、「ATL レジストリ コンポーネント (レジストラー)」](../../atl/atl-registry-component-registrar.md)を参照してください。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
