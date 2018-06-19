---
title: CComCoClass クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
dev_langs:
- C++
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 738d7e937acf2d3299be97b4f091c698582911d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365463"
---
# <a name="ccomcoclass-class"></a>CComCoClass クラス
このクラスは、クラスのインスタンスを作成して、そのプロパティを取得するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, const CLSID* pclsid = &CLSID_NULL>  
class CComCoClass
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`CComCoClass`です。  
  
 *pclsid*  
 オブジェクトの CLSID へのポインター。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[あって](#createinstance)|(静的)クラスとインターフェイスのクエリのインスタンスを作成します。|  
|[CComCoClass::Error](#error)|(静的)クライアントに詳細なエラー情報を返します。|  
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(静的)オブジェクトのクラス識別子を返します。|  
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(静的)オブジェクトの説明を返すようにオーバーライドします。|  
  
## <a name="remarks"></a>コメント  
 `CComCoClass` オブジェクトの CLSID を取得する、エラー情報を設定すると、クラスのインスタンスを作成するには、メソッドを提供します。 登録されている任意のクラス、[オブジェクト マップ](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f)から派生する必要があります`CComCoClass`です。  
  
 `CComCoClass` また、オブジェクトの既定のクラス ファクトリと集計モデルを定義します。 `CComCoClass` 次の 2 つのマクロを使用します。  
  
- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)を宣言するクラス ファクトリ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)です。  
  
- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)オブジェクトを集計できることを宣言します。  
  
 これらの既定値のいずれかのクラスの定義で別のマクロを指定することによってオーバーライドできます。 例については、使用する[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)の代わりに`CComClassFactory`を指定して、 [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)マクロ。  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="createinstance"></a>  あって  
 これらを使用して`CreateInstance`COM のインスタンスを作成する関数オブジェクトし、COM API を使用せずにインターフェイス ポインターを取得します。  
  
```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `Q`  
 COM インターフェイス経由で返される`pp`です。  
  
 *punkOuter*  
 [in]外部の不明なまたは集計の制御不明です。  
  
 `pp`  
 [out]作成が成功した場合、要求されたインターフェイス ポインターを受け取るポインター変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。 参照してください[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)戻り値の詳細については、Windows SDK に含まれています。  
  
### <a name="remarks"></a>コメント  
 この関数の最初のオーバー ロードを使用して、一般的なオブジェクトの作成には作成されるオブジェクトを集計する必要がある場合は、2 番目のオーバー ロードを使用します。  
  
 必須の COM オブジェクトを実装する ATL クラス (最初のテンプレート パラメーターとして使用されるクラスは、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)) 呼び出し元のコードと同じプロジェクトである必要があります。 COM オブジェクトの作成は、この ATL クラスに登録されているクラスのファクトリによって実行されます。  
  
 これらの関数を使用して外部で作成されてからできないように設定したオブジェクトの作成に役立つ、[役立つ](object-map-macros.md#object_entry_non_createable_ex_auto)マクロです。 これらもを効率よく行うのために COM API を避けたい場合に便利です。  
  
 なお、インターフェイス`Q`IID が関連付けられていることを使用して取得できる必要があります、 [_ _uuidof](../../cpp/uuidof-operator.md)演算子。  
  
### <a name="example"></a>例  
 次の例では、`CDocument`から ATL ウィザードで生成されたクラスが派生`CComCoClass`を実装する、 **IDocument**インターフェイスです。 クラスは、オブジェクトのマップに、`OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`マクロ クライアントを使用して、ドキュメントのインスタンスを作成できないように[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)です。 `CApplication` ドキュメント クラスのインスタンスを作成する独自の COM インターフェイスの 1 つのメソッドを提供するコクラスがします。 簡単な方法は次のコード、ドキュメントを使用してクラスのインスタンスを作成するために、`CreateInstance`から継承されたメンバー、`CComCoClass`基本クラスです。  
  
 [!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="error"></a>  CComCoClass::Error  
 この静的関数、`IErrorInfo`エラー情報をクライアントに提供するインターフェイスです。  
  
```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDesc`  
 [in]エラーを説明する文字列。 Unicode バージョン`Error`ことを指定`lpszDesc`の種類は**LPCOLESTR**; ANSI バージョンの種類を指定する`LPCSTR`です。  
  
 `iid`  
 [in]エラーを定義するインターフェイスの IID または`GUID_NULL`(既定値)、エラーが、オペレーティング システムで定義されている場合。  
  
 `hRes`  
 [in]`HRESULT`する呼び出し元に返されます。 既定値は 0 です。 詳細については`hRes`、「解説」を参照してください。  
  
 `nID`  
 [in]エラーを説明する文字列が格納されているリソースの識別子。 この値は、包括的 0x0200 と 0 xffff、間にする必要があります。 デバッグ ビルドで、 **ASSERT**なります`nID`有効な文字列のインデックスは作成されません。 リリース ビルドでエラーを説明する文字列を「不明なエラー」に設定されます。  
  
 `dwHelpID`  
 [in]エラーのヘルプ コンテキスト id。  
  
 `lpszHelpFile`  
 [in]パスとエラーを説明するヘルプ ファイルの名前。  
  
 `hInst`  
 [in]リソースへのハンドル。 このパラメーターは、既定では、 **_AtlModule::GetResourceInstance**ここで、 **_AtlModule**のグローバル インスタンスは、[不要](../../atl/reference/catlmodule-class.md)です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 呼び出す`Error`、オブジェクトを実装する必要があります、`ISupportErrorInfo Interface`インターフェイスです。  
  
 場合、`hRes`パラメーターが 0 以外の場合、`Error`の値を返します`hRes`です。 場合`hRes`が 0 の場合、最初の 4 つのバージョンの`Error`返す`DISP_E_EXCEPTION`です。 最後の 2 つのバージョンは、マクロの結果を返す**MAKE_HRESULT (1, FACILITY_ITF、** `nID` **)** です。  
  
##  <a name="getobjectclsid"></a>  CComCoClass::GetObjectCLSID  
 一貫性のあるオブジェクトの CLSID を取得する方法を提供します。  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトのクラス識別子です。  
  
##  <a name="getobjectdescription"></a>  CComCoClass::GetObjectDescription  
 この静的関数は、クラス オブジェクトのテキストの説明を取得します。  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>戻り値  
 クラスのオブジェクトの説明です。  
  
### <a name="remarks"></a>コメント  
 既定の実装を返します**NULL**です。 このメソッドをオーバーライドすることができます、 [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description)マクロです。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription` によって呼び出される**IComponentRegistrar::GetComponents**です。 **IComponentRegistrar**オートメーション インターフェイスを使用すると、登録および登録解除、DLL 内の個々 のコンポーネントです。 ATL プロジェクト ウィザードを使用してコンポーネント レジスタのオブジェクトを作成するときに、ウィザードは自動的に実装、 **IComponentRegistrar**インターフェイスです。 **IComponentRegistrar**は通常 Microsoft Transaction Server によって使用されます。  
  
 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトを作成する](../../atl/reference/creating-an-atl-project.md)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
