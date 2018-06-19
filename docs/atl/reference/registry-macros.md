---
title: レジストリ マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed9b172217f1ca7ada7d8752151126b53055df37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365218"
---
# <a name="registry-macros"></a>レジストリ マクロ
これらのマクロでは、便利タイプ ライブラリとレジストリの機能を定義します。  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL. への依存関係を避けるために、オブジェクト内にあるオブジェクトの登録のコードをすることを示しますDLL です。|  
|[DECLARE_LIBID](#declare_libid)|ATL を取得する方法を提供、 *libid*のタイプ ライブラリ。|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|既定の ATL の登録を回避できます。|  
|[DECLARE_REGISTRY](#declare_registry)|入力またはシステム レジストリの主要なオブジェクトのエントリを削除します。|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|自動的に登録するために必要な情報を指定します、 *appid*です。|  
|[に](#declare_registry_resource)|名前付きリソースを検索して、レジストリ スクリプトを実行します。|  
|[代入](#declare_registry_resourceid)|ID 番号で識別されるリソースを検索して、レジストリ スクリプトを実行します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
    
##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY  
 ATL. への依存関係を避けるために、オブジェクト内にあるオブジェクトの登録コードするかを示す記号DLL です。  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>コメント  
 定義するときに**ATL_STATIC_REGISTRY**、次のコードを使用する必要があります。  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="declare_libid"></a>  DECLARE_LIBID  
 ATL を取得する方法を提供、 *libid*のタイプ ライブラリ。  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>パラメーター  
 *libid*  
 タイプ ライブラリの GUID です。  
  
### <a name="remarks"></a>コメント  
 使用して`DECLARE_LIBID`で、 `CAtlModuleT`-クラスを派生します。  
  
### <a name="example"></a>例  
 ウィザードで生成された ATL プロジェクトの属性なしでは、このマクロを使用するサンプルがあります。  
  
##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY  
 使用して`DECLARE_NO_REGISTRY`このマクロが表示されるクラスの既定 ATL 登録されないようにする場合。  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="declare_registry"></a>  DECLARE_REGISTRY  
 システム レジストリに標準的なクラスの登録を入力またはシステム レジストリから削除します。  
  
```
DECLARE_REGISTRY(
    class, 
    pid, 
    vpid, 
    nid, 
    flags )
```  
  
### <a name="parameters"></a>パラメーター  
 `class`  
 [in]旧バージョンとの互換性のために含まれています。  
  
 `pid`  
 [in]`LPCTSTR`されているバージョンに固有のプログラムの識別子。  
  
 *vpid*  
 [in]`LPCTSTR`されているバージョンに依存しないプログラム id。  
  
 *nid*  
 [in]A **UINT**つまりプログラムの説明として使用するレジストリ内のリソース文字列のインデックス。  
  
 `flags`  
 [in]A`DWORD`プログラムが含まれていると、レジストリ内のモデルのスレッドします。 次の値のいずれかを指定する必要があります: **THREADFLAGS_APARTMENT**、 **THREADFLAGS_BOTH**、または**AUTPRXFLAG**です。  
  
### <a name="remarks"></a>コメント  
 標準の登録は、CLSID、プログラム ID、バージョンに依存しないプログラム ID、説明する文字列、およびスレッド モデルで構成されます。  
  
 ウィザードが自動的にレジストリのスクリプト ベースのサポートを実装し、追加オブジェクトを作成またはクラスの追加ウィザードを使用して制御するときに、[代入](#declare_registry_resourceid)ファイルにマクロです。 スクリプト ベースのレジストリ サポートしたくない場合は、このマクロを置き換える必要があります。`DECLARE_REGISTRY`です。 `DECLARE_REGISTRY` のみ、レジストリに上で説明した 5 つの基本的なキーを挿入します。 手動でレジストリに他のキーを挿入するコードを記述する必要があります。  
  
##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID  
 自動的に登録するために必要な情報を指定します、 *appid*です。  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>パラメーター  
 *resid*  
 に関する情報を含む .rgs ファイルのリソース id、 *appid*です。  
  
 *appid*  
 GUID。  
  
### <a name="remarks"></a>コメント  
 使用して`DECLARE_REGISTRY_APPID_RESOURCEID`で、 `CAtlModuleT`-クラスを派生します。  
  
### <a name="example"></a>例  
 クラスの追加コード ウィザードを使用して ATL プロジェクトに追加するクラスをこのマクロを使用するサンプルが含まれます。  
  
##  <a name="declare_registry_resource"></a>  に  
 レジストリ ファイルを含む名前付きリソースを取得し、システム レジストリにオブジェクトを入力するか、それらをシステム レジストリから削除するスクリプトを実行します。  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]文字列リソースの識別子。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを作成または ATL プロジェクト ウィザードを使用して制御するときにウィザードが自動的にレジストリのスクリプト ベースのサポートを実装し、追加、[代入](#declare_registry_resourceid)に似ていますが、マクロ`DECLARE_REGISTRY_RESOURCE`をファイル。  
  
 最適化されたレジストリへのアクセスの ATL レジストリ コンポーネント (レジストラー) と静的にリンクすることができます。 レジストラー コードに静的にリンクするには、stdafx.h ファイルに次の行を追加します。  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 ATL 実行時に置換値を代わりに使用する場合を指定しない、`DECLARE_REGISTRY_RESOURCE`または`DECLARE_REGISTRY_RESOURCEID`マクロです。 配列を作成する代わりに、**結果**実行時に、プレース ホルダーを置換する値を持つ対応する構造体、各エントリに変数のプレース ホルダーが含まれています。 呼び出す[として](catlmodule-class.md#updateregistryfromresourced)または[方法については](catlmodule-class.md#updateregistryfromresources)配列を渡します。 すべての置換値の追加、**結果**レジストラーの置換マップする構造体。  

  
 置き換え可能パラメーターおよびスクリプトに関する詳細については、記事を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)です。  
  
##  <a name="declare_registry_resourceid"></a>  代入  
 同じ[に](#declare_registry_resource)ウィザードで生成されたを使用する点を除いて**UINT**を文字列名ではなく、リソースを識別します。  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]ウィザードで生成されたリソースの識別子。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを作成または ATL プロジェクト ウィザードを使用して制御するときにウィザードが自動的にレジストリのスクリプト ベースのサポートを実装し、追加、`DECLARE_REGISTRY_RESOURCEID`ファイルにマクロです。  
  
 最適化されたレジストリへのアクセスの ATL レジストリ コンポーネント (レジストラー) と静的にリンクすることができます。 レジストラー コードに静的にリンクするには、stdafx.h ファイルに次の行を追加します。  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 ATL 実行時に置換値を代わりに使用する場合を指定しない、`DECLARE_REGISTRY_RESOURCE`または`DECLARE_REGISTRY_RESOURCEID`マクロです。 配列を作成する代わりに、**結果**実行時に、プレース ホルダーを置換する値を持つ対応する構造体、各エントリに変数のプレース ホルダーが含まれています。 呼び出す[として](catlmodule-class.md#updateregistryfromresourced)または[方法については](catlmodule-class.md#updateregistryfromresources)配列を渡します。 すべての置換値の追加、**結果**レジストラーの置換マップする構造体。  

  
 置き換え可能パラメーターおよびスクリプトに関する詳細については、記事を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)です。  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
