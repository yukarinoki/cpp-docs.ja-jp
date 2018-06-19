---
title: オブジェクトのマップに関するマクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
dev_langs:
- C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 671fd80bc2c4ad320efb282fd659899756c2ecbc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362944"
---
# <a name="object-map-macros"></a>オブジェクト マップに関するマクロ
これらのマクロは、オブジェクトのマップとエントリを定義します。  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|オブジェクト マップに入力は、クラス オブジェクトのテキストの説明を指定できます。|  
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|オブジェクト マップに ATL オブジェクトを入力オブジェクトのインスタンスを作成し、レジストリを更新します。|  
|[役立つ](#object_entry_non_createable_ex_auto)|オブジェクトを登録して初期化するように指定する一方で、`CoCreateInstance` を使用してオブジェクトを外部で作成できないように指定できます。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="declare_object_description"></a>  DECLARE_OBJECT_DESCRIPTION  
 クラスのオブジェクトの説明文を指定できます。  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]クラスのオブジェクトの説明です。  
  
### <a name="remarks"></a>コメント  
 ATL を介してオブジェクト マップにこの説明を入力する、 [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd)マクロです。  
  
 `DECLARE_OBJECT_DESCRIPTION` 実装する、`GetObjectDescription`関数をオーバーライドして使用できる、 [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription)メソッドです。  

  
 `GetObjectDescription`によって呼び出されます**IComponentRegistrar::GetComponents**です。 **IComponentRegistrar**オートメーション インターフェイスを使用すると、登録および登録解除、DLL 内の個々 のコンポーネントです。 ATL プロジェクト ウィザードを使用してコンポーネント レジスタのオブジェクトを作成するときに、ウィザードは自動的に実装、 **IComponentRegistrar**インターフェイスです。 **IComponentRegistrar**は通常 Microsoft Transaction Server によって使用されます。  
  
 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトを作成する](../../atl/reference/creating-an-atl-project.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>  OBJECT_ENTRY_AUTO  
 オブジェクト マップに ATL オブジェクトを入力オブジェクトのインスタンスを作成し、レジストリを更新します。  
  
```
OBJECT_ENTRY_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [入力] `class` という名前の C++ クラスで実装されている COM クラスの CLSID。  
  
 `class`  
 [入力] `clsid` で表される COM クラスを実装する C++ クラスの名前。  
  
### <a name="remarks"></a>コメント  
 オブジェクトのエントリ マクロは、クラスの登録、初期化、および作成をサポートするためにプロジェクトのグローバル スコープに配置されます。  
  
 `OBJECT_ENTRY_AUTO` クリエーター クラスおよびクラス ファクトリ クリエーター クラスの関数ポインターが入る`CreateInstance`ATL オブジェクトの自動生成されたマップには、このオブジェクトの関数。 ときに[CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)が呼び出されると、オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。  

  
 次の表では、このマクロを 2 番目のパラメーターとして指定されているクラスからオブジェクト マップに追加される情報を取得する方法について説明します。  
  
|情報|取得|  
|---------------------|-------------------|  
|COM 登録|[レジストリに関するマクロ](../../atl/reference/registry-macros.md)|  
|クラス ファクトリの作成|[クラス ファクトリ マクロ](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|インスタンスの作成|[集約マクロ](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|コンポーネントのカテゴリの登録|[カテゴリに関するマクロ](../../atl/reference/category-macros.md)|  
|クラス レベルの初期化とクリーンアップ|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

  
##  <a name="object_entry_non_createable_ex_auto"></a>  役立つ  
 オブジェクトを登録して初期化するように指定する一方で、`CoCreateInstance` を使用してオブジェクトを外部で作成できないように指定できます。  
  
```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [入力] `class` という名前の C++ クラスで実装されている COM クラスの CLSID。  
  
 `class`  
 [入力] `clsid` で表される COM クラスを実装する C++ クラスの名前。  
  
### <a name="remarks"></a>コメント  
 オブジェクトのエントリ マクロは、クラスの登録、初期化、および作成をサポートするためにプロジェクトのグローバル スコープに配置されます。  
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO` オブジェクトを登録して初期化することを指定することができます (を参照してください[OBJECT_ENTRY_AUTO](#object_entry_auto)詳細については) を使用して作成する必要がありますされませんが、`CoCreateInstance`です。  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
