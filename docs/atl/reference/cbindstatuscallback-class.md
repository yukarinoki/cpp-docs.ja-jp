---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
ms.openlocfilehash: 6cdac444836574dd4d398571b71bb25363af5d3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321229"
---
# <a name="cbindstatuscallback-class"></a>クラス

このクラスによって、`IBindStatusCallback` インターフェイスが実装されます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
データを受信する場合に呼び出される関数を含むクラス。

*フラグを設定します。*<br/>
[GetBindInfo](#getbindinfo)によって返されるバインド フラグを指定します。 既定の実装では、バインドを非同期に設定し、最新バージョンのデータ/オブジェクトを取得し、取得したデータをディスク キャッシュに格納しません。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コールバック::Cバインドステータスコールバック](#cbindstatuscallback)|コンストラクターです。|
|[コールバック:~Cバインドステータスコールバック](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コールバック::Dのロード](#download)|ダウンロード プロセスを開始し、オブジェクトを`CBindStatusCallback`作成し、呼び`StartAsyncDownload`出す静的メソッド。|
|[コールバックを取得します。](#getbindinfo)|作成するバインドの種類に関する情報を要求するために、非同期モニカーによって呼び出されます。|
|[コールバックを取得します。](#getpriority)|バインド操作の優先順位を取得するために、非同期モニカーによって呼び出されます。 ATL の実装`E_NOTIMPL`は、 を返します。|
|[を使用できます。](#ondataavailable)|アプリケーションが使用可能になったときにデータを提供するために呼び出されます。 データを読み取り、渡された関数を呼び出してデータを使用します。|
|[リソースを設定します。](#onlowresource)|リソースが少ないときに呼び出されます。 ATL 実装はS_OKを返します。|
|[利用可能なオブジェクト](#onobjectavailable)|アプリケーションにオブジェクト インターフェイス ポインターを渡すために、非同期モニカーによって呼び出されます。 ATL 実装はS_OKを返します。|
|[コールバック::オンプログレス](#onprogress)|データのダウンロード プロセスの進行状況を示すために呼び出されます。 ATL 実装はS_OKを返します。|
|[バインドステータスコールバック::オンスタートバインディング](#onstartbinding)|バインディングが開始されたときに呼び出されます。|
|[バインド状態コールバック::オンストップバインディング](#onstopbinding)|非同期データ転送が停止したときに呼び出されます。|
|[をクリックします。](#startasyncdownload)|使用可能なバイト数と読み取りバイトをゼロに初期化し、URL からプッシュ型ストリーム オブジェクト`OnDataAvailable`を作成し、データが使用可能になるたびに呼び出します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コールバック:m_dwAvailableToRead](#m_dwavailabletoread)|読み取り可能なバイト数。|
|[コールバック:m_dwTotalRead](#m_dwtotalread)|読み取られたバイト数の合計。|
|[コールバック:m_pFunc](#m_pfunc)|データが使用可能な場合に呼び出される関数へのポインター。|
|[コールバック:m_pT](#m_pt)|非同期データ転送を要求するオブジェクトへのポインター。|
|[コールバック:m_spBindCtx](#m_spbindctx)|現在のバインド操作の[IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx)インターフェイスへのポインター。|
|[コールバック:m_spBinding](#m_spbinding)|現在の`IBinding`バインド操作のインターフェイスへのポインター。|
|[コールバック:m_spMoniker](#m_spmoniker)|使用する URL の[IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)インターフェイスへのポインター。|
|[コールバック:m_spStream](#m_spstream)|データ転送の[IStream](/windows/win32/api/objidl/nn-objidl-istream)インターフェイスへのポインター。|

## <a name="remarks"></a>解説

`CBindStatusCallback` クラスによって、`IBindStatusCallback` インターフェイスが実装されます。 `IBindStatusCallback`非同期データ転送から通知を受信できるように、アプリケーションによって実装する必要があります。 システムによって提供される非同期モニカーは、メソッド`IBindStatusCallback`を使用して、オブジェクトとの間での非同期データ転送に関する情報の送受信を行います。

通常、オブジェクト`CBindStatusCallback`は特定のバインド操作に関連付けられます。 たとえば[、ASYNC](../../overview/visual-cpp-samples.md)サンプルでは、URL プロパティを設定すると、`CBindStatusCallback``Download`の呼び出しでオブジェクトが作成されます。

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

非同期モニカーは、コールバック関数`OnData`を使用して、データがある場合にアプリケーションを呼び出します。 非同期モニカーはシステムによって提供されます。

## <a name="inheritance-hierarchy"></a>継承階層

`CComObjectRootBase`

`IBindStatusCallback`

[ココムオブジェクトルート](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="cbindstatuscallback"></a>コールバック::Cバインドステータスコールバック

コンストラクターです。

```
CBindStatusCallback();
```

### <a name="remarks"></a>解説

非同期データ転送に関する通知を受け取るオブジェクトを作成します。 通常、バインド操作ごとに 1 つのオブジェクトが作成されます。

コンストラクターは[、m_pT](#m_pt)を初期化し、null に[m_pFunc](#m_pfunc)します。

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="dtor"></a>コールバック:~Cバインドステータスコールバック

デストラクターです。

```
~CBindStatusCallback();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="cbindstatuscallbackdownload"></a><a name="download"></a>コールバック::Dのロード

オブジェクトを`CBindStatusCallback`作成し、`StartAsyncDownload`指定した URL から非同期的にデータのダウンロードを開始する呼び出しを行います。

```
static HRESULT Download(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
[in]非同期データ転送を要求するオブジェクトへのポインター。 オブジェクト`CBindStatusCallback`は、このオブジェクトのクラスでテンプレート化されます。

*を見る*<br/>
[in]読み取られるデータを受け取る関数へのポインター。 関数は、オブジェクトのクラスの型 のメンバーです`T`。 構文と例については[、「StartAsyncDownload」](#startasyncdownload)を参照してください。

*bstrURL*<br/>
[in]データの取得元の URL。 任意の有効な URL またはファイル名を指定できます。 Nll は指定できません。 次に例を示します。

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*コンテナを確認する*<br/>
[in]コンテナー`IUnknown`の。 既定では NULL です。

*b相対的な*<br/>
[in]URL が相対 URL か絶対 URL かを示すフラグ。 既定では FALSE で、URL は絶対 URL です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

データが使用可能なたびに、 を介して`OnDataAvailable`オブジェクトに送信されます。 `OnDataAvailable`データを読み取り *、pFunc*が指す関数を呼び出します (たとえば、データを保存したり、画面に出力したり)。

## <a name="cbindstatuscallbackgetbindinfo"></a><a name="getbindinfo"></a>コールバックを取得します。

モニカーにバインドする方法を伝えるために呼び出されます。

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>パラメーター

*を使用する*<br/>
[アウト]バインド操作の発生方法を示す BINDF 列挙値へのポインター。 既定では、次の列挙値を使用して設定されます。

非同期ダウンロードBINDF_ASYNCHRONOUSします。

BINDF_ASYNCSTORAGE`OnDataAvailable`は、データが使用可能になるまでブロックするのではなく、データがまだ利用できない場合にE_PENDINGを返します。

BINDF_GETNEWESTVERSION バインド操作では、最新バージョンのデータを取得する必要があります。

BINDF_NOWRITECACHE バインド操作では、取得したデータをディスク キャッシュに格納しないでください。

*プバインドインフォ*<br/>
[イン、アウト]オブジェクトがバインディングをどのように`BINDINFO`行いたいかについての詳細情報を与える構造体へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

既定の実装では、非同期にバインドを設定し、データ プッシュ モデルを使用します。 データ プッシュ モデルでは、モニカーは非同期バインド操作を実行し、新しいデータが使用可能になったときにクライアントに継続的に通知します。

## <a name="cbindstatuscallbackgetpriority"></a><a name="getpriority"></a>コールバックを取得します。

バインド操作の優先順位を取得するために、非同期モニカーによって呼び出されます。

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>パラメーター

*優先順位*<br/>
[アウト]成功時に優先順位を受け取る**LONG**変数のアドレス。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

## <a name="cbindstatuscallbackm_dwavailabletoread"></a><a name="m_dwavailabletoread"></a>コールバック:m_dwAvailableToRead

読み取り可能なバイト数を格納するために使用できます。

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>解説

で`StartAsyncDownload`0 に初期化されます。

## <a name="cbindstatuscallbackm_dwtotalread"></a><a name="m_dwtotalread"></a>コールバック:m_dwTotalRead

非同期データ転送で読み取られたバイトの累積合計。

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>解説

毎回`OnDataAvailable`インクリメントは、実際に読み取られたバイト数によって呼び出されます。 で`StartAsyncDownload`0 に初期化されます。

## <a name="cbindstatuscallbackm_pfunc"></a><a name="m_pfunc"></a>コールバック:m_pFunc

指し示される`m_pFunc`関数は、使用可能`OnDataAvailable`なデータを読み取った後 (たとえば、データを保存したり画面に出力したりする場合) に呼び出されます。

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>解説

が`m_pFunc`指す関数は、オブジェクトのクラスのメンバーであり、次の構文を持ちます。

```
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

## <a name="cbindstatuscallbackm_pt"></a><a name="m_pt"></a>コールバック:m_pT

非同期データ転送を要求するオブジェクトへのポインター。

```
T* m_pT;
```

### <a name="remarks"></a>解説

オブジェクト`CBindStatusCallback`は、このオブジェクトのクラスでテンプレート化されます。

## <a name="cbindstatuscallbackm_spbindctx"></a><a name="m_spbindctx"></a>コールバック:m_spBindCtx

バインド コンテキスト (特定のモニカー バインド操作に関する情報を格納するオブジェクト) へのアクセスを提供する[IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx)インターフェイスへのポインター。

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>解説

で`StartAsyncDownload`初期化されます。

## <a name="cbindstatuscallbackm_spbinding"></a><a name="m_spbinding"></a>コールバック:m_spBinding

現在のバインド操作`IBinding`のインターフェイスへのポインター。

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>解説

で`OnStartBinding`初期化され、`OnStopBinding`でリリースされます。

## <a name="cbindstatuscallbackm_spmoniker"></a><a name="m_spmoniker"></a>コールバック:m_spMoniker

使用する URL の[IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)インターフェイスへのポインター。

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>解説

で`StartAsyncDownload`初期化されます。

## <a name="cbindstatuscallbackm_spstream"></a><a name="m_spstream"></a>コールバック:m_spStream

現在のバインド操作の[IStream](/windows/win32/api/objidl/nn-objidl-istream)インターフェイスへのポインター。

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>解説

BCSF`STGMEDIUM`フラグがBCSF_FIRSTDATANOTIFICATIONされ、BCSF フラグがBCSF_LASTDATANOTIFICATIONされたときに解放されるときに、構造体`OnDataAvailable`から初期化されます。

## <a name="cbindstatuscallbackondataavailable"></a><a name="ondataavailable"></a>を使用できます。

システム提供の非同期モニカーは、オブジェクト`OnDataAvailable`が使用可能になったときにデータを提供するために呼び出します。

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>パラメーター

*グルフブスCF*<br/>
[in]BSCF 列挙値。 BSCF_FIRSTDATANOTIFICATION、BSCF_INTERMEDIARYDATANOTIFICATION、またはBSCF_LASTDATANOTIFICATIONのいずれかまたは複数。

*Dwsize*<br/>
[in]バインドの開始以降に使用可能なデータの累積量 (バイト単位)。 データ量が関連性が無いか、または特定の量が使用できなくなったことを示すゼロを指定できます。

*pフォーマット*<br/>
[in]使用可能なデータの形式を含む[FORMATETC](/windows/win32/com/the-formatetc-structure)構造体へのポインター。 フォーマットがない場合は、CF_NULLできます。

*pstgmed*<br/>
[in]現在利用可能な実際のデータを保持する[STGMEDIUM](/windows/win32/com/the-stgmedium-structure)構造体へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

`OnDataAvailable`データを読み取り、オブジェクトのクラスのメソッドを呼び出します (たとえば、データを格納したり、画面に出力したり)。 詳細については[、次](#startasyncdownload)を参照してください。

## <a name="cbindstatuscallbackonlowresource"></a><a name="onlowresource"></a>リソースを設定します。

リソースが少ないときに呼び出されます。

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>パラメーター

*dw予約済み*<br/>
予約済み。

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="cbindstatuscallbackonobjectavailable"></a><a name="onobjectavailable"></a>利用可能なオブジェクト

アプリケーションにオブジェクト インターフェイス ポインターを渡すために、非同期モニカーによって呼び出されます。

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
要求されたインターフェイスのインターフェイス識別子。 未使用。

*パンク*<br/>
IUnknown インターフェイスのアドレス。 未使用。

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="cbindstatuscallbackonprogress"></a><a name="onprogress"></a>コールバック::オンプログレス

データのダウンロード プロセスの進行状況を示すために呼び出されます。

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>パラメーター

*ウルプログレス*<br/>
符号なし長整数。 未使用。

*ウルプログレスマックス*<br/>
符号なし長整数 未使用。

*州の状況コード*<br/>
符号なし長整数。 未使用。

*テキスト*<br/>
文字列値のアドレス。 未使用。

### <a name="return-value"></a>戻り値

S_OKを返します。

## <a name="cbindstatuscallbackonstartbinding"></a><a name="onstartbinding"></a>バインドステータスコールバック::オンスタートバインディング

データ メンバ[のm_spBinding](#m_spbinding)を`IBinding`*pBinding*のポインタに設定します。

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>パラメーター

*dw予約済み*<br/>
将来利用するために予約されています。

*バインディング*<br/>
[in]現在のバインド操作の IBinding インターフェイスのアドレス。 NULL にすることはできません。 クライアントは、バインド オブジェクトへの参照を保持するには、このポインターで AddRef を呼び出す必要があります。

## <a name="cbindstatuscallbackonstopbinding"></a><a name="onstopbinding"></a>バインド状態コールバック::オンストップバインディング

データ`IBinding`メンバのポインタを[解放m_spBinding。](#m_spbinding)

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>パラメーター

*Hresult*<br/>
バインド操作から返された状態コード。

*エラー*<br/>
文字列値のアドレス。 未使用。

### <a name="remarks"></a>解説

バインド操作の終了を示すために、システム提供の非同期モニカーによって呼び出されます。

## <a name="cbindstatuscallbackstartasyncdownload"></a><a name="startasyncdownload"></a>をクリックします。

指定した URL から非同期的にデータのダウンロードを開始します。

```
HRESULT StartAsyncDownload(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
[in]非同期データ転送を要求するオブジェクトへのポインター。 オブジェクト`CBindStatusCallback`は、このオブジェクトのクラスでテンプレート化されます。

*を見る*<br/>
[in]読み取り対象のデータを受け取る関数へのポインター。 関数は、オブジェクトのクラスの型 のメンバーです`T`。 構文と例については **、「解説」** を参照してください。

*bstrURL*<br/>
[in]データの取得元の URL。 任意の有効な URL またはファイル名を指定できます。 Nll は指定できません。 次に例を示します。

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*コンテナを確認する*<br/>
[in]コンテナー`IUnknown`の。 既定では NULL です。

*b相対的な*<br/>
[in]URL が相対 URL か絶対 URL かを示すフラグ。 既定では FALSE で、URL は絶対 URL です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

データが使用可能なたびに、 を介して`OnDataAvailable`オブジェクトに送信されます。 `OnDataAvailable`データを読み取り *、pFunc*が指す関数を呼び出します (たとえば、データを保存したり、画面に出力したり)。

*pFunc*が指す関数は、オブジェクトのクラスのメンバーであり、次の構文を持ちます。

```
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

次の例[(ASYNC](../../overview/visual-cpp-samples.md)サンプルから取得) では`OnData`、関数は受信したデータをテキスト ボックスに書き込みます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
