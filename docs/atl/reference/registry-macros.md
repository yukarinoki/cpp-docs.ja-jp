---
title: レジストリに関するマクロ
ms.date: 11/04/2016
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
ms.openlocfilehash: 8e05d6a47ea67138e8d1d456077526dd3178cc44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274643"
---
# <a name="registry-macros"></a>レジストリに関するマクロ

これらのマクロは、便利な型のライブラリとレジストリの機能を定義します。

|||
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL. への依存関係を回避するために、オブジェクトであるオブジェクトの登録コードをすることを示しますDLL です。|
|[DECLARE_LIBID](#declare_libid)|ATL を取得する方法を提供します、 *libid*のタイプ ライブラリ。|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|既定の ATL 登録を回避できます。|
|[DECLARE_REGISTRY](#declare_registry)|入るか、システム レジストリの主要なオブジェクトのエントリを削除します。|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|自動的に登録するために必要な情報を指定します、 *appid*します。|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|名前付きリソースを検索し、レジストリ スクリプトを実行します。|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|ID 番号で識別されるリソースを検索し、レジストリ スクリプトを実行します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY

ATL. への依存関係を回避するために、オブジェクトであるオブジェクトの登録コードをするかを示すシンボルDLL です。

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>Remarks

ATL_STATIC_REGISTRY を定義するときに、次のコードを使用する必要があります。

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

##  <a name="declare_libid"></a>  DECLARE_LIBID

ATL を取得する方法を提供します、 *libid*のタイプ ライブラリ。

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>パラメーター

*libid*<br/>
タイプ ライブラリの GUID です。

### <a name="remarks"></a>Remarks

DECLARE_LIBID を使用して、 `CAtlModuleT`-クラスを派生します。

### <a name="example"></a>例

ATL ウィザードで生成されたプロジェクトの以外の属性は、このマクロを使用してサンプルを必要があります。

##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY

このマクロが表示されるクラスの既定 ATL 登録しないようにする場合は、DECLARE_NO_REGISTRY を使用します。

```
DECLARE_NO_REGISTRY()
```

##  <a name="declare_registry"></a>  DECLARE_REGISTRY

システム レジストリに標準のクラスの登録が入るか、システム レジストリから削除されます。

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
[in]旧バージョンとの互換性のために含まれています。

*pid*<br/>
[in]バージョン固有のプログラム識別子である LPCTSTR します。

*vpid*<br/>
[in]バージョンに依存しないプログラム識別子である LPCTSTR します。

*nid*<br/>
[in]プログラムの説明として使用するレジストリ内のリソース文字列のインデックスである UINT します。

*flags*<br/>
[in]レジストリで、プログラムのスレッド処理モデルを含む DWORD。 値は次のいずれかを指定する必要があります。THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG します。

### <a name="remarks"></a>Remarks

標準の登録は、CLSID、プログラム ID、バージョンに依存しないプログラム ID、説明文字列、およびスレッド モデルで構成されます。

ウィザードが自動的にレジストリのスクリプト ベースのサポートを実装し、追加オブジェクトを作成またはクラスの追加ウィザードを使用して制御するときに、[代入](#declare_registry_resourceid)ファイルにマクロ。 レジストリのスクリプト ベースのサポートしたくない場合は、このマクロを DECLARE_REGISTRY に置き換える必要があります。 DECLARE_REGISTRY のみ、レジストリに上記で説明した 5 つの基本的なキーを挿入します。 手動でレジストリにその他のキーを挿入するコードを記述する必要があります。

##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID

自動的に登録するために必要な情報を指定します、 *appid*します。

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>パラメーター

*resid*<br/>
に関する情報を含む .rgs ファイルのリソース id、 *appid*します。

*appid*<br/>
GUID。

### <a name="remarks"></a>Remarks

DECLARE_REGISTRY_APPID_RESOURCEID を使用して、 `CAtlModuleT`-クラスを派生します。

### <a name="example"></a>例

クラスの追加コード ウィザードを使用して、ATL プロジェクトに追加されたクラスは、このマクロを使用してサンプルを必要があります。

##  <a name="declare_registry_resource"></a>  DECLARE_REGISTRY_RESOURCE

レジストリ ファイルを含む名前付きリソースを取得し、システム レジストリにオブジェクトを入力するか、システム レジストリから削除するスクリプトを実行します。

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
[in]リソースの識別子の文字列を指定します。

### <a name="remarks"></a>Remarks

ウィザードのレジストリのスクリプト ベースのサポートを実装し、追加は自動的にオブジェクトを作成または ATL プロジェクト ウィザードを使用して制御するときに、[代入](#declare_registry_resourceid)DECLARE_REGISTRY_ に似ていますが、マクロファイルへのリソースです。

最適化されたレジストリへのアクセスの ATL レジストリ コンポーネント (レジストラー) で静的にリンクすることができます。 レジストラー コードに静的にリンクするには、stdafx.h ファイルに次の行を追加します。

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL 実行時に置換値を置換する場合は、代入マクロを指定しません。 配列を作成する代わりに、`_ATL_REGMAP_ENTRIES`構造、各エントリが変数のプレース ホルダーが含まれている実行時に、プレース ホルダーを置換する値と組み合わせて使用します。 呼び出して[として](catlmodule-class.md#updateregistryfromresourced)または[方法については](catlmodule-class.md#updateregistryfromresources)配列を渡します。 これは、すべての置換値の追加、`_ATL_REGMAP_ENTRIES`レジストラーの置換のマップの構造体。

置き換え可能パラメーターとスクリプト作成する方法の詳細については、記事を参照してください。 [、ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。

##  <a name="declare_registry_resourceid"></a>  DECLARE_REGISTRY_RESOURCEID

同じ[に](#declare_registry_resource)をウィザードで生成された UINT 文字列名ではなく、リソースを識別するために使用します。

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
[in]ウィザードで生成された、リソースの識別子。

### <a name="remarks"></a>Remarks

オブジェクトまたは ATL プロジェクト ウィザードを使用してコントロールを作成するときに、ウィザードは自動的にレジストリのスクリプト ベースのサポートを実装し、ファイルに代入マクロを追加します。

最適化されたレジストリへのアクセスの ATL レジストリ コンポーネント (レジストラー) で静的にリンクすることができます。 レジストラー コードに静的にリンクするには、stdafx.h ファイルに次の行を追加します。

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL 実行時に置換値を置換する場合は、代入マクロを指定しません。 配列を作成する代わりに、`_ATL_REGMAP_ENTRIES`構造、各エントリが変数のプレース ホルダーが含まれている実行時に、プレース ホルダーを置換する値と組み合わせて使用します。 呼び出して[として](catlmodule-class.md#updateregistryfromresourced)または[方法については](catlmodule-class.md#updateregistryfromresources)配列を渡します。 これは、すべての置換値の追加、`_ATL_REGMAP_ENTRIES`レジストラーの置換のマップの構造体。

置き換え可能パラメーターとスクリプト作成する方法の詳細については、記事を参照してください。 [、ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)
