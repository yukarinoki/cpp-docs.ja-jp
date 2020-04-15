---
title: CComCoクラスクラス
ms.date: 11/04/2016
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
ms.openlocfilehash: 11e724a982f3a2f404473dbdd34d848842cc8e14
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320836"
---
# <a name="ccomcoclass-class"></a>CComCoクラスクラス

このクラスには、クラスのインスタンスを作成し、そのプロパティを取得するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`CComCoClass`。

*pclsid*<br/>
オブジェクトの CLSID へのポインター。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[インスタンスを作成します。](#createinstance)|(静的)クラスのインスタンスを作成し、インターフェイスを照会します。|
|[CComCoクラス::エラー](#error)|(静的)リッチ エラー情報をクライアントに返します。|
|[クラス::オブジェクトのクラスを取得します。](#getobjectclsid)|(静的)オブジェクトのクラス識別子を返します。|
|[オブジェクトの説明を取得します。](#getobjectdescription)|(静的)オーバーライドしてオブジェクトの説明を返します。|

## <a name="remarks"></a>解説

`CComCoClass`には、オブジェクトの CLSID を取得するメソッド、エラー情報を設定するメソッド、およびクラスのインスタンスを作成するためのメソッドが用意されています。 オブジェクト マップに登録されているクラスは、 から`CComCoClass`派生する必要があります。

`CComCoClass`また、オブジェクトの既定のクラス ファクトリと集計モデルも定義します。 `CComCoClass`では、次の 2 つのマクロを使用します。

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)クラス ファクトリを[CCom クラス ファクトリ](../../atl/reference/ccomclassfactory-class.md)として宣言します。

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)オブジェクトを集計できることを宣言します。

クラス定義で別のマクロを指定すると、これらのデフォルトのいずれかをオーバーライドできます。 たとえば、 の代わりに[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) `CComClassFactory`を使用するには[、DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2)マクロを指定します。

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomcoclasscreateinstance"></a><a name="createinstance"></a>インスタンスを作成します。

これらの`CreateInstance`関数を使用して、COM オブジェクトのインスタンスを作成し、COM API を使用せずにインターフェイス ポインターを取得します。

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>パラメーター

*Q*<br/>
*pp*を介して返される COM インターフェイス。

*パンクアウター*<br/>
[in]外部不明または制御の集合体の不明。

*頁*<br/>
[アウト]作成が成功した場合に、要求されたインターフェイス ポインターを受け取るポインター変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。 可能な戻り値の詳細については、Windows SDK の[CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)を参照してください。

### <a name="remarks"></a>解説

この関数の最初のオーバーロードは、一般的なオブジェクトの作成に使用します。作成するオブジェクトを集約する必要がある場合は、2 番目のオーバーロードを使用します。

必要な COM オブジェクト ([つまり、CComCoClass](../../atl/reference/ccomcoclass-class.md)の最初のテンプレート パラメーターとして使用されるクラス) を実装する ATL クラスは、呼び出し元のコードと同じプロジェクト内になければなりません。 COM オブジェクトの作成は、この ATL クラスに登録されたクラス ファクトリによって実行されます。

これらの関数は[、OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto)マクロを使用して外部で作成不可能なオブジェクトを作成する場合に便利です。 また、効率の高い理由から COM API を回避したい場合にも役立ちます。

インターフェイス*Q*には[、__uuidof](../../cpp/uuidof-operator.md)演算子を使用して取得できる IID が関連付けられている必要があることに注意してください。

### <a name="example"></a>例

次の例では、`CDocument`インターフェイスを実装`CComCoClass`するから派生したウィザード生成 ATL クラス`IDocument`を示します。 クラスは、クライアントが[CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)を使用してドキュメントのインスタンスを作成できないように、OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO マクロを使用してオブジェクト マップに登録されます。 `CApplication`は、独自の COM インターフェイスの 1 つで、ドキュメント クラスのインスタンスを作成するメソッドを提供する CoClass です。 次のコードは、基本クラスから継承されたメンバーを使用してドキュメント クラス`CreateInstance`のインスタンスを簡単`CComCoClass`に作成する方法を示しています。

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

## <a name="ccomcoclasserror"></a><a name="error"></a>CComCoクラス::エラー

この静的関数は、エラー`IErrorInfo`情報をクライアントに提供するインターフェイスを設定します。

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

*lpszDesc*<br/>
[in]エラーを説明する文字列。 のユニコード・バージョン`Error`は *、lpszDesc*がタイプ LPCOLESTR であることを指定します。ANSI バージョンは LPCSTR の種類を指定します。

*Iid*<br/>
[in]エラーを定義するインターフェイスの IID またはGUID_NULL (既定値) (オペレーティング システムによってエラーが定義されている場合)。

*hRes*<br/>
[in]呼び出し元に返される HRESULT。 既定値は 0 です。 *hRes*の詳細については、「解説」を参照してください。

*nID*<br/>
[in]エラー記述文字列が格納されるリソース識別子。 この値は 0x0200 から 0xFFFF の間にあって、包括的に指定する必要があります。 デバッグ ビルドでは *、nID*が有効な文字列にインデックスを付けていない場合 **、ASSERT**が生成されます。 リリース ビルドでは、エラーの説明文字列が "不明なエラー" に設定されます。

*ヘルプID*<br/>
[in]エラーのヘルプ コンテキスト識別子。

*ファイル*<br/>
[in]エラーを説明するヘルプ ファイルのパスと名前。

*hInst*<br/>
[in]リソースへのハンドル。 既定では、このパラメーター`_AtlModule::GetResourceInstance``_AtlModule`は 、 [CAtlModule](../../atl/reference/catlmodule-class.md)のグローバル インスタンスです。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

を呼`Error`び出すためには、オブジェクト`ISupportErrorInfo Interface`がインターフェイスを実装する必要があります。

*hRes*パラメータが 0 以外の`Error`場合は *、hRes*の値を返します。 *hRes*がゼロの場合、戻り値の`Error`最初の 4 つのバージョンDISP_E_EXCEPTION。 最後の 2 つのバージョンは、マクロ**MAKE_HRESULT( 1, FACILITY_ITF,** *nID* )**の**結果を返します。

## <a name="ccomcoclassgetobjectclsid"></a><a name="getobjectclsid"></a>クラス::オブジェクトのクラスを取得します。

オブジェクトの CLSID を取得する一貫した方法を提供します。

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>戻り値

オブジェクトのクラス識別子。

## <a name="ccomcoclassgetobjectdescription"></a><a name="getobjectdescription"></a>オブジェクトの説明を取得します。

この静的関数は、クラス オブジェクトのテキストの説明を取得します。

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>戻り値

クラス オブジェクトの説明。

### <a name="remarks"></a>解説

既定の実装では NULL が返されます。 このメソッドは[、DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description)マクロでオーバーライドできます。 次に例を示します。

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription`によって呼び`IComponentRegistrar::GetComponents`出されます。 `IComponentRegistrar`は、DLL 内の個々のコンポーネントを登録および登録解除できるオートメーション インターフェイスです。 ATL プロジェクト ウィザードを使用してコンポーネント レジストラー オブジェクトを作成すると、ウィザードによって自動的`IComponentRegistrar`にインターフェイスが実装されます。 `IComponentRegistrar`は通常、マイクロソフトのトランザクション サーバーによって使用されます。

ATL プロジェクト ウィザードの詳細については、ATL[プロジェクトの作成に関する記事を](../../atl/reference/creating-an-atl-project.md)参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
