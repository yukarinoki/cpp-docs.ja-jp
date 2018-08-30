---
title: CBindStatusCallback クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8879c1d304e6d46b7ae3c8c2f1ed535526a5390e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202463"
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback クラス
このクラスは、`IBindStatusCallback` インターフェイスを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS |   BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx
 <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 データを受信すると呼び出される関数を含むクラスです。  
  
 *nBindFlags*  
 によって返されるバインド フラグを指定[GetBindInfo](#getbindinfo)します。 既定の実装を非同期にするバインドを設定するには、データ オブジェクトの最新バージョンを取得およびディスク キャッシュを取得したデータを保存しません。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|コンストラクターです。|  
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|ダウンロード プロセスを開始する静的メソッドを作成、`CBindStatusCallback`オブジェクト、および呼び出し`StartAsyncDownload`します。|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|非同期モニカーを作成するバインドの種類に関する情報を要求によって呼び出されます。|  
|[CBindStatusCallback::GetPriority](#getpriority)|バインド操作の優先順位を取得する非同期モニカーによって呼び出されます。 ATL の実装を返します`E_NOTIMPL`します。|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|使用可能になったようにアプリケーションにデータを提供すると呼ばれます。 データを読み取るし、データを使用するために渡される関数を呼び出します。|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|リソースが少ないときに呼び出されます。 ATL の実装では、S_OK を返します。|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|アプリケーションにオブジェクトのインターフェイス ポインターを渡す非同期モニカーによって呼び出されます。 ATL の実装では、S_OK を返します。|  
|[CBindStatusCallback::OnProgress](#onprogress)|データのダウンロード処理の進行状況を示すために呼び出されます。 ATL の実装では、S_OK を返します。|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|バインドが開始されたときに呼び出されます。|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|非同期データ転送が停止したときに呼び出されます。|  
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|使用可能なバイトを初期化し、URL、および呼び出しからプッシュ型のストリーム オブジェクトを作成する 0 に読み取られたバイト数`OnDataAvailable`データがあるたびにします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|読み取り可能バイト数。|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|読み取られたバイトの合計数。|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|関数へのポインターでは、データがあるときに呼び出されます。|  
|[CBindStatusCallback::m_pT](#m_pt)|非同期データ転送を要求しているオブジェクトへのポインター。|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|ポインター、 [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx)現在のバインド操作のインターフェイス。|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|ポインター、`IBinding`現在のバインド操作のインターフェイス。|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|ポインター、 [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)インターフェイスを使用する URL。|  
|[CBindStatusCallback::m_spStream](#m_spstream)|ポインター、 [IStream](/windows/desktop/api/objidl/nn-objidl-istream)データ転送のインターフェイス。|  
  
## <a name="remarks"></a>Remarks  
 `CBindStatusCallback` クラスは、`IBindStatusCallback` インターフェイスを実装します。 `IBindStatusCallback` 非同期データ転送をから通知を受信できるように、アプリケーションで実装する必要があります。 システムによって提供される非同期モニカーを使用して`IBindStatusCallback`非同期データに関する情報を送受信する方法と、オブジェクトの間を転送します。  
  
 通常、`CBindStatusCallback`オブジェクトが特定のバインド操作に関連付けられています。 たとえば、[非同期](../../visual-cpp-samples.md)サンプルでは、URL プロパティを設定するときに作成、`CBindStatusCallback`オブジェクトへの呼び出しで`Download`:  
  
 [!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 非同期モニカーがコールバック関数を使用して`OnData`データがあるときに、アプリケーションを呼び出す。 非同期モニカーは、システムによって提供されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="cbindstatuscallback"></a>  CBindStatusCallback::CBindStatusCallback  
 コンストラクターです。  
  
```
CBindStatusCallback();
```  
  
### <a name="remarks"></a>Remarks  
 非同期データ転送に関する通知を受信するオブジェクトを作成します。 通常、バインド操作ごとに 1 つのオブジェクトが作成されます。  
  
 コンス トラクターによって初期化も[この](#m_pt)と[m_pFunc](#m_pfunc)を NULL にします。  
  
##  <a name="dtor"></a>  CBindStatusCallback:: ~ CBindStatusCallback  
 デストラクターです。  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>Remarks  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="download"></a>  CBindStatusCallback::Download  
 作成、`CBindStatusCallback`オブジェクトと呼び出し`StartAsyncDownload`指定した URL からデータを非同期的にダウンロードを開始します。  
  
```
static HRESULT Download(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 [in]非同期データ転送を要求しているオブジェクトへのポインター。 `CBindStatusCallback`オブジェクトは、このオブジェクトのクラスでテンプレート化されます。  
  
 *pFunc*  
 [in]読み取られるデータを受信する関数へのポインター。 関数型のオブジェクトのクラスのメンバーである`T`します。 参照してください[このポインターは](#startasyncdownload)構文と例。  
  
 *bstrURL*  
 [in]データの取得元の URL。 有効な URL またはファイル名を指定できます。 Nll は指定できません。 例えば:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 *pUnkContainer*  
 [in]`IUnknown`のコンテナー。 既定では NULL です。  
  
 *bRelative*  
 [in]URL が相対または絶対かどうかを示すフラグです。 つまり、URL が既定で FALSE は絶対です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 使用してオブジェクトに送信されるデータがあるたびに`OnDataAvailable`します。 `OnDataAvailable` データを読み取り、によって示される関数を呼び出す*pFunc* (たとえば、データを格納したり、画面に出力する場合)。  
  
##  <a name="getbindinfo"></a>  CBindStatusCallback::GetBindInfo  
 モニカー バインドする方法を指示するには、呼び出されます。  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *pgrfBSCF*  
 [out]バインド操作を行う方法を示す BINDF 列挙値へのポインター。 既定では、次の列挙値を設定します。  
  
 BINDF_ASYNCHRONOUS 非同期ダウンロードします。  
  
 BINDF_ASYNCSTORAGE`OnDataAvailable`データがまだデータが利用可能になるまでのブロックではなく利用できない場合は、E_PENDING を返します。  
  
 BINDF_GETNEWESTVERSION バインド操作では、データの最新バージョンを取得する必要があります。  
  
 ディスク キャッシュ内のデータを取得する BINDF_NOWRITECACHE バインド操作を格納しないでください。  
  
 *pbindinfo*  
 [入力、出力]ポインター、`BINDINFO`構造オブジェクトで発生するバインドを希望する方法の詳細を提供します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、非同期にして、データ プッシュ モデルを使用するバインディングを設定します。 データ プッシュ モデルでは、モニカーは、バインドの非同期操作し、継続的に新しいデータがあるたびにクライアントに通知します。  
  
##  <a name="getpriority"></a>  CBindStatusCallback::GetPriority  
 バインド操作の優先順位を取得する非同期モニカーによって呼び出されます。  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnPriority*  
 [out]アドレス、**長い**成功した場合、優先順位を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
##  <a name="m_dwavailabletoread"></a>  CBindStatusCallback::m_dwAvailableToRead  
 読み取り可能なバイト数を格納するために使用します。  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>Remarks  
 0 に初期化された`StartAsyncDownload`します。  
  
##  <a name="m_dwtotalread"></a>  CBindStatusCallback::m_dwTotalRead  
 非同期データ転送での読み取り総バイト数。  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>Remarks  
 たびにインクリメント`OnDataAvailable`は実際に読み取られたバイト数によって呼び出されます。 0 に初期化された`StartAsyncDownload`します。  
  
##  <a name="m_pfunc"></a>  CBindStatusCallback::m_pFunc  
 によって示される関数`m_pFunc`によって呼び出される`OnDataAvailable`後 (たとえば、データを格納したり、画面に出力する場合など) の使用可能なデータを読み取ります。  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>Remarks  
 によって示される関数`m_pFunc`オブジェクトのクラスのメンバーであるし、は、次の構文。  
  
```  
void Function_Name(  
   CBindStatusCallback<T>* pbsc,  
   BYTE* pBytes,  
   DWORD dwSize  
   );  
```  
  
##  <a name="m_pt"></a>  CBindStatusCallback::m_pT  
 非同期データ転送を要求しているオブジェクトへのポインター。  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>Remarks  
 `CBindStatusCallback`オブジェクトは、このオブジェクトのクラスでテンプレート化されます。  
  
##  <a name="m_spbindctx"></a>  CBindStatusCallback::m_spBindCtx  
 ポインター、 [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx)バインド コンテキスト (特定のモニカー バインド操作に関する情報を格納するオブジェクト) へのアクセスを提供するインターフェイスです。  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>Remarks  
 初期化された`StartAsyncDownload`します。  
  
##  <a name="m_spbinding"></a>  CBindStatusCallback::m_spBinding  
 ポインター、`IBinding`現在のバインド操作のインターフェイス。  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>Remarks  
 初期化された`OnStartBinding`でリリースされた`OnStopBinding`します。  
  
##  <a name="m_spmoniker"></a>  CBindStatusCallback::m_spMoniker  
 ポインター、 [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)インターフェイスを使用する URL。  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>Remarks  
 初期化された`StartAsyncDownload`します。  
  
##  <a name="m_spstream"></a>  CBindStatusCallback::m_spStream  
 ポインター、 [IStream](/windows/desktop/api/objidl/nn-objidl-istream)現在のバインド操作のインターフェイス。  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>Remarks  
 初期化された`OnDataAvailable`から、 `STGMEDIUM` BCSF フラグは BCSF_FIRSTDATANOTIFICATION され BCSF フラグは BCSF_LASTDATANOTIFICATION 時に解放構造体します。  
  
##  <a name="ondataavailable"></a>  CBindStatusCallback::OnDataAvailable  
 システムが提供する非同期モニカー呼び出し`OnDataAvailable`を使用可能になったオブジェクトにデータを提供します。  
  
```
STDMETHOD(  
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```  
  
### <a name="parameters"></a>パラメーター  
 *grfBSCF*  
 [in]BSCF 列挙値。 次のいずれかまたは: BSCF_FIRSTDATANOTIFICATION、BSCF_INTERMEDIARYDATANOTIFICATION、または知らせるします。  
  
 *ない dwSize*  
 [in]バインディングの当初から使用可能なデータのバイト単位で累積時間。 データの量に関連がないこと、または特定の量が利用できないことを示す、0 にすることができます。  
  
 *pformatetc*  
 [in]ポインター、 [FORMATETC](/windows/desktop/com/the-formatetc-structure)使用可能なデータの形式を格納する構造体。 形式がない場合は、CF_NULL を指定できます。  
  
 *pstgmed*  
 [in]ポインター、 [STGMEDIUM](/windows/desktop/com/the-stgmedium-structure)今すぐに利用可能な実際のデータを保持する構造体。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 `OnDataAvailable` データを読み取り、(たとえば、データを格納したり、画面に出力する場合)、オブジェクトのクラスのメソッドを呼び出します。 参照してください[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)詳細についてはします。  
  
##  <a name="onlowresource"></a>  CBindStatusCallback::OnLowResource  
 リソースが少ないときに呼び出されます。  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwReserved*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="onobjectavailable"></a>  CBindStatusCallback::OnObjectAvailable  
 アプリケーションにオブジェクトのインターフェイス ポインターを渡す非同期モニカーによって呼び出されます。  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>パラメーター  
 *riid*  
 要求されたインターフェイスのインターフェイスの識別子です。 使用されません。  
  
 *punk*  
 IUnknown インターフェイスのアドレス。 使用されません。  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="onprogress"></a>  CBindStatusCallback::OnProgress  
 データのダウンロード処理の進行状況を示すために呼び出されます。  
  
```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```  
  
### <a name="parameters"></a>パラメーター  
 *ulProgress*  
 符号なし long 整数。 使用されません。  
  
 *ulProgressMax*  
 符号なし long 整数未使用。  
  
 *ulStatusCode*  
 符号なし long 整数。 使用されません。  
  
 *szStatusText*  
 文字列値のアドレス。 使用されません。  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
##  <a name="onstartbinding"></a>  CBindStatusCallback::OnStartBinding  
 データ メンバーを設定[m_spBinding](#m_spbinding)を`IBinding`ポインター *pBinding*します。  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwReserved*  
 将来使用するために予約されています。  
  
 *pBinding*  
 [in]現在のアドレスは、操作をバインドします。 これは、NULL を使用できません。 クライアントは、バインディング オブジェクトへの参照を保持するには、このポインターに AddRef を呼び出す必要があります。  
  
##  <a name="onstopbinding"></a>  CBindStatusCallback::OnStopBinding  
 リリース、`IBinding`データ メンバー内のポインター [m_spBinding](#m_spbinding)します。  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>パラメーター  
 *hresult*  
 バインド操作から返されるステータス コード。  
  
 szStatusText  
 文字列値の未使用のアドレス。  
  
### <a name="remarks"></a>Remarks  
 バインド操作の終了を示すシステム提供の非同期モニカーによって呼び出されます。  
  
##  <a name="startasyncdownload"></a>  CBindStatusCallback::StartAsyncDownload  
 指定した URL からデータを非同期的にダウンロードを開始します。  
  
```
HRESULT StartAsyncDownload(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 [in]非同期データ転送を要求しているオブジェクトへのポインター。 `CBindStatusCallback`オブジェクトは、このオブジェクトのクラスでテンプレート化されます。  
  
 *pFunc*  
 [in]読み取られるデータを受信する関数へのポインター。 関数型のオブジェクトのクラスのメンバーである`T`します。 参照してください**解説**構文と例。  
  
 *bstrURL*  
 [in]データの取得元の URL。 有効な URL またはファイル名を指定できます。 Nll は指定できません。 例えば:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 *pUnkContainer*  
 [in]`IUnknown`のコンテナー。 既定では NULL です。  
  
 *bRelative*  
 [in]URL が相対または絶対かどうかを示すフラグです。 つまり、URL が既定で FALSE は絶対です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 使用してオブジェクトに送信されるデータがあるたびに`OnDataAvailable`します。 `OnDataAvailable` データを読み取り、によって示される関数を呼び出す*pFunc* (たとえば、データを格納したり、画面に出力する場合)。  
  
 によって示される関数*pFunc*オブジェクトのクラスのメンバーであるし、は、次の構文。  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD` `dwSize`  
  
 `);`  
  
 次の例 (から取得した、 [ASYNC](../../visual-cpp-samples.md)サンプル)、関数は、`OnData`テキスト ボックスに、受信したデータを書き込みます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
