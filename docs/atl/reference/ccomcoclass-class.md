---
title: CComCoClass クラス |Microsoft Docs
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
ms.openlocfilehash: 693a0e63e5fe67b1a3837ae71945ccc60b5fb247
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204344"
---
# <a name="ccomcoclass-class"></a>CComCoClass クラス
このクラスは、クラスのインスタンスを作成し、そのプロパティを取得するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, const CLSID* pclsid = &CLSID_NULL>  
class CComCoClass
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`CComCoClass`します。  
  
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
  
## <a name="remarks"></a>Remarks  
 `CComCoClass` オブジェクトの CLSID を取得する、エラー情報を設定およびクラスのインスタンスを作成するメソッドを提供します。 登録されている任意のクラス、[オブジェクト マップ](https://msdn.microsoft.com/b57619cc-534f-4b8f-bfd4-0c12f937202f)から派生する必要があります`CComCoClass`します。  
  
 `CComCoClass` また、オブジェクトの既定のクラス ファクトリと集計モデルを定義します。 `CComCoClass` 次の 2 つのマクロを使用します。  
  
- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)宣言をクラス ファクトリ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)します。  
  
- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)オブジェクトを集計できることを宣言します。  
  
 これらの既定値のいずれかのクラスの定義で別のマクロを指定することによってオーバーライドできます。 たとえば、使用する[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)の代わりに`CComClassFactory`、指定、 [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)マクロ。  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="createinstance"></a>  あって  
 これらを使用して、 `CreateInstance` COM のインスタンスを作成する関数オブジェクトし、COM API を使用せず、インターフェイス ポインターを取得します。  
  
```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 *Q*  
 COM インターフェイス経由で返される*pp*します。  
  
 *punkOuter*  
 [in]不明な外部または集計の unknown を制御します。  
  
 *pp*  
 [out]作成が成功した場合は、要求されたインターフェイス ポインターを受け取るポインター変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。 参照してください[CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance) Windows sdk の有効な戻り値の説明。  
  
### <a name="remarks"></a>Remarks  
 この関数の最初のオーバー ロードを使用して、一般的なオブジェクトを作成します。作成されるオブジェクトを集計する必要がある場合は、2 番目のオーバー ロードを使用します。  
  
 必要な COM オブジェクトを実装する ATL クラス (最初のテンプレート パラメーターとして使用されるクラスは、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)) 呼び出し元のコードと同じプロジェクトである必要があります。 COM オブジェクトの作成は、この ATL クラスに登録されているクラスのファクトリによって実行されます。  
  
 これらの関数を使用して外部で作成されていることを避けがオブジェクトの作成に役立つ、[役立つ](object-map-macros.md#object_entry_non_createable_ex_auto)マクロ。 効率を上げるのために COM API を回避する場合に便利です。  
  
 なお、インターフェイス*Q* IID が関連付けられていることを使用して取得できる必要があります、 [_ _uuidof](../../cpp/uuidof-operator.md)演算子。  
  
### <a name="example"></a>例  
 次の例では、 `CDocument` ATL ウィザードで生成されたクラスから派生`CComCoClass`を実装する、`IDocument`インターフェイス。 クラスが役立つマクロを持つオブジェクトのマップに登録されてクライアントを使用して、ドキュメントのインスタンスを作成できないため[CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)します。 `CApplication` ドキュメント クラスのインスタンスを作成する独自の COM インターフェイスの 1 つのメソッドを提供するコクラスです。 いかに簡単かを示す次のコードを使用してドキュメント クラスのインスタンスを作成、`CreateInstance`から継承されたメンバー、`CComCoClass`基本クラス。  
  
 [!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="error"></a>  CComCoClass::Error  
 この静的関数、`IErrorInfo`エラー情報をクライアントに提供するインターフェイス。  
  
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
 *lpszDesc*  
 [in]エラーを説明する文字列。 Unicode バージョン`Error`ことを指定します*lpszDesc*の入力 LPCOLESTR; ANSI バージョンは、LPCSTR の種類を指定します。  
 *iid*  
 [in]エラーがオペレーティング システムによって定義されている場合は、エラーまたは GUID_ (既定値) を定義するインターフェイスの IID。  
  
 *hRes*  
 [in]呼び出し元に必要な HRESULT が返されます。 既定値は 0 です。 詳細については*hRes*、「解説」を参照してください。  
  
 *nID*  
 [in]エラー説明文字列が格納されているリソースの識別子です。 この値は 0x0200 と 0 xffff の範囲である必要があります。 デバッグ ビルドで、 **ASSERT**なります*nID*有効な文字列のインデックスを作成しません。 リリース ビルドでエラーを説明する文字列を「不明なエラー」に設定されます。  
  
 *dwHelpID*  
 [in]エラーのヘルプ コンテキスト識別子。  
  
 *lpszHelpFile*  
 [in]パスとエラーを説明するヘルプ ファイルの名前。  
  
 *hInst*  
 [in]リソースへのハンドル。 このパラメーターは、既定では、`_AtlModule::GetResourceInstance`ここで、`_AtlModule`のグローバル インスタンス[CAtlModule](../../atl/reference/catlmodule-class.md)します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`Error`、オブジェクトを実装する必要があります、`ISupportErrorInfo Interface`インターフェイス。  
  
 場合、 *hRes*パラメーターは、0 以外の場合、`Error`の値を返します*hRes*します。 場合*hRes*が 0 の最初の 4 つのバージョン`Error`DISP_E_EXCEPTION を返します。 最後の 2 つのバージョンが、マクロの結果を返す**MAKE_HRESULT (1, FACILITY_ITF、** *nID* **)** します。  
  
##  <a name="getobjectclsid"></a>  CComCoClass::GetObjectCLSID  
 一貫性のあるオブジェクトの CLSID を取得する方法を提供します。  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトのクラスの識別子です。  
  
##  <a name="getobjectdescription"></a>  CComCoClass::GetObjectDescription  
 この静的関数は、クラス オブジェクトの説明テキストを取得します。  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>戻り値  
 クラス オブジェクトの説明です。  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、NULL を返します。 このメソッドをオーバーライドすることができます、 [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description)マクロ。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription` によって呼び出される`IComponentRegistrar::GetComponents`します。 `IComponentRegistrar` オートメーション インターフェイスを登録し、DLL 内の個々 のコンポーネントの登録を解除することができますです。 ATL プロジェクト ウィザードでコンポーネント レジストラー オブジェクトを作成するときに、ウィザードは自動的に実装、`IComponentRegistrar`インターフェイス。 `IComponentRegistrar` 通常、Microsoft Transaction Server によって使用されます。  
  
 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
