---
title: CAsyncMonikerFile クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
dev_langs:
- C++
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16d4b5169ffa93892b8a3076cbfa24227ccf569f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile クラス
ActiveX コントロール (以前の OLE コントロール) で非同期モニカーを使用するための機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|`CAsyncMonikerFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncMonikerFile::Close](#close)|閉じるし、すべてのリソースを解放します。|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|非同期転送バインドへのポインターを取得します。|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|ストリーム内のデータの形式を取得します。|  
|[CAsyncMonikerFile::Open](#open)|非同期的にファイルを開きます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|実装する COM オブジェクトを作成`IBindStatusCallback`です。|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|作成するバインドの種類に関する情報を要求する OLE システム ライブラリによって呼び出されます。|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|バインディングの優先度を取得する OLE システム ライブラリによって呼び出されます。|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|非同期バインド操作中に、クライアントに利用可能になったデータを提供するには、呼び出されます。|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|リソースが低いときに呼び出されます。|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|データのダウンロード処理の進行状況を示すために呼び出されます。|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|バインディングが開始されるときに呼び出されます。|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|非同期転送が停止したときに呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 派生した[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)からさらに派生した[関数](../../mfc/reference/colestreamfile-class.md)、`CAsyncMonikerFile`を使用して、 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)任意のデータ ストリームにアクセスするインターフェイス非同期的に、URL から非同期的にファイルの読み込みにも含まれます。 ファイルは、ActiveX コントロールのデータパス プロパティであることができます。  
  
 非同期モニカーは、ファイル転送中に、応答性の高いユーザー インターフェイスを提供するインターネット対応のアプリケーションと ActiveX コントロールで、主に使用されます。 この主要な例は、の使用[関数](../../mfc/reference/cdatapathproperty-class.md)ActiveX コントロールの非同期プロパティを指定します。 `CDataPathProperty`オブジェクトは、時間のかかるプロパティ exchange プロセス中に新しいデータの可用性を通知するコールバックを取得して繰り返しです。  
  
 インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次の記事を参照してください。  
  
- [インターネット最初のステップ: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [インターネット最初のステップ: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [関数](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="casyncmonikerfile"></a>  CAsyncMonikerFile::CAsyncMonikerFile  
 `CAsyncMonikerFile` オブジェクトを構築します。  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>コメント  
 作成されません、`IBindHost`インターフェイスです。 `IBindHost` 指定した場合にのみに使用、**開く**メンバー関数。  
  
 詳細については、`IBindHost`インターフェイスでは、Windows SDK を参照してください。  
  
##  <a name="close"></a>  CAsyncMonikerFile::Close  
 この関数では、閉じ、すべてのリソースを解放します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 開かれていないか、既に閉じられているファイルに呼び出すことができます。  
  
##  <a name="createbindstatuscallback"></a>  CAsyncMonikerFile::CreateBindStatusCallback  
 実装する COM オブジェクトを作成`IBindStatusCallback`です。  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkControlling`  
 Controlling unknown へのポインター (外側**IUnknown**) または**NULL**集計が使用されていない場合。  
  
### <a name="return-value"></a>戻り値  
 場合`pUnkControlling`は**NULL**、関数の内部にポインターを返します**IUnknown** 、新しい COM オブジェクトのサポートに`IBindStatusCallback`です。 場合`pUnkControlling`は**NULL**へのポインターを返します、 **IUnknown** 、新しい COM オブジェクトのサポートに`IBindStatusCallback`です。  
  
### <a name="remarks"></a>コメント  
 `CAsyncMonikerFile` 実装する COM オブジェクトが必要です`IBindStatusCallback`です。 MFC は、このようなオブジェクトを実装し、集計可能であります。 オーバーライドできます`CreateBindStatusCallback`独自の COM オブジェクトを取得します。 呼び出すことによって、COM オブジェクトが MFC の実装を集計できる`CreateBindStatusCallback`COM オブジェクトの制御、不明なとします。 使用して実装されている COM オブジェクト、 `CCmdTarget` COM サポートを制御する不明なを使用して、取得できます**CCmdTarget::GetControllingUnknown**です。  
  
 COM オブジェクトを呼び出すことで MFC の実装に委任できます代わりに、 **CreateBindStatusCallback (NULL)** です。  
  
 [CAsyncMonikerFile::Open](#open)呼び出し`CreateBindStatusCallback`です。  
  
 非同期モニカーおよび非同期のバインドの詳細については、次を参照してください。、 [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060)インターフェイスと[非同期バインド方法と記憶域作業](http://msdn.microsoft.com/library/windows/desktop/aa379152)です。 集計の詳細については、次を参照してください。[集計](http://msdn.microsoft.com/library/windows/desktop/ms686558)です。 3 つすべてのトピックは、Windows SDK には。  
  
##  <a name="getbindinfo"></a>  CAsyncMonikerFile::GetBindInfo  
 非同期モニカーをバインドする方法を確認する非同期モニカーのクライアントから呼び出されます。  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>戻り値  
 設定を取得**IBindStatusCallBack**です。 詳細については、`IBindStatusCallback`インターフェイスでは、Windows SDK を参照してください。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、非同期、記憶域メディア (ストリーム) を使用し、データ プッシュ モデルを使用するバインディングを設定します。 バインディングの動作を変更する場合は、この関数をオーバーライドします。  
  
 これを行うための 1 つの理由は、データ プッシュ モデルではなくデータ プル モデルを使用してバインドすることです。 データ プル モデルでは、クライアントがバインド操作を駆動し、モニカーのみデータをクライアントに提供が読み取られるとします。 データ プッシュ モデルでは、モニカーは、バインドの非同期操作を駆動し、継続的に新しいデータがあるたびにクライアントに通知します。  
  
##  <a name="getbinding"></a>  CAsyncMonikerFile::GetBinding  
 非同期転送バインドへのポインターを取得するには、この関数を呼び出します。  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`IBinding`非同期転送が開始されるときに提供されるインターフェイス。 返します**NULL**何らかの理由で、転送を実行できない場合に非同期的にします。  
  
### <a name="remarks"></a>コメント  
 これにより、データ転送プロセスを通じてコントロールを`IBinding`インターフェイス例についてで**IBinding::Abort**、 **IBinding::Pause**、および**IBinding::Resume**.  
  
 詳細については、`IBinding`インターフェイスでは、Windows SDK を参照してください。  
  
##  <a name="getformatetc"></a>  CAsyncMonikerFile::GetFormatEtc  
 ストリーム内のデータの形式を取得するには、この関数を呼び出します。  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows の構造体へのポインター [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)現在開いているストリーム。 返します**NULL**モニカーがバインドされていない場合、非同期ではない場合、または非同期操作が開始されていない場合。  
  
##  <a name="getpriority"></a>  CAsyncMonikerFile::GetPriority  
 バインディング プロセスの開始を受け取るための優先順位のスレッドにバインド操作と非同期モニカーのクライアントから呼び出されます。  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>戻り値  
 優先順位を非同期的に転送を行います。 標準スレッドの優先順位フラグのいずれかの: **THREAD_PRIORITY_ABOVE_NORMAL**、 **THREAD_PRIORITY_BELOW_NORMAL**、 **THREAD_PRIORITY_HIGHEST**、 **THREAD_PRIORITY_IDLE**、 **THREAD_PRIORITY_LOWEST**、 **THREAD_PRIORITY_NORMAL**、および**THREAD_PRIORITY_TIME_CRITICAL**です。 Windows の関数を参照してください[SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)これらの値の詳細についてはします。  
  
### <a name="remarks"></a>コメント  
 `GetPriority` 呼び出すことはできません直接です。 **THREAD_PRIORITY_NORMAL**が既定の実装によって返されます。  
  
##  <a name="ondataavailable"></a>  CAsyncMonikerFile::OnDataAvailable  
 非同期モニカーは`OnDataAvailable`を指定するデータをクライアントに使用可能になったら、非同期の中に、バインド操作します。  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwSize`  
 累積的な量 (バイト) をデータ バインドの開始以降で使用可能です。 データの量が、操作に関連するかいる特定の量が利用できないことを示す、0 にすることができます。  
  
 *bscfFlag*  
 A **BSCF**列挙値。 次の値の 1 つ以上を指定できます。  
  
- **BSCF_FIRSTDATANOTIFICATION**を識別する最初の呼び出し`OnDataAvailable`操作が指定されたバインド。  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION**を識別するための中間の呼び出し`OnDataAvailable`バインド操作します。  
  
- **知らせる**最後の呼び出しを識別`OnDataAvailable`バインド操作します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 実装のサンプルについては、次の例を参照してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="onlowresource"></a>  CAsyncMonikerFile::OnLowResource  
 リソースが低いときに、モニカーによって呼び出されます。  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装`GetBinding( )-> Abort( )`です。  
  
##  <a name="onprogress"></a>  CAsyncMonikerFile::OnProgress  
 モニカー バインド操作、時間のかかる操作中に適切な間隔で通常の現在の進行状況を示すために繰り返しによって呼び出されます。  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>パラメーター  
 `ulProgress`  
 示される予想最大相対バインド操作の現在の進行状況を示す`ulProgressMax`です。  
  
 `ulProgressMax`  
 予想最大値を示す`ulProgress`への呼び出しの間`OnProgress`この操作にします。  
  
 `ulStatusCode`  
 バインド操作の進行状況に関する追加情報を提供します。 有効な値から取得されますが、`BINDSTATUS`列挙します。 使用可能な値は、「解説」を参照してください。  
  
 `szStatusText`  
 値に応じて、現在の進行状況に関する情報`ulStatusCode`です。 使用可能な値は、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 指定できる値`ulStatusCode`(および`szStatusText`値ごとに) は。  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 バインド操作では、オブジェクトにバインドされている記憶域を含むリソースを見つけることです。 `szStatusText`検索対象となるリソースの表示名を提供 (たとえば、"www.microsoft.com") にします。  
  
 **BINDSTATUS_CONNECTING**  
 バインド操作は、オブジェクトにバインドされている記憶域を含むリソースに接続します。 `szStatusText` (たとえば、IP アドレス) に接続されているリソースの表示名を提供します。  
  
 **BINDSTATUS_SENDINGREQUEST**  
 バインド操作は、オブジェクトまたはにバインドされているストレージに要求しています。 `szStatusText`オブジェクト (たとえば、ファイル名) の表示名を提供します。  
  
 **BINDSTATUS_REDIRECTING**  
 バインド操作は、さまざまなデータの場所にリダイレクトされています。 `szStatusText`データの新しい場所の表示名を提供します。  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 バインド操作は、キャッシュされたコピーから、記憶域、要求されたオブジェクトを取得しています。 `szStatusText`は**NULL**です。  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 バインド操作では、オブジェクトまたはにバインドされているストレージの受信を開始しました。 `szStatusText`データの場所の表示名を提供します。  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 バインド操作にバインドされている記憶域、オブジェクトを受信し続けます。 `szStatusText`データの場所の表示名を提供します。  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 バインド操作では、オブジェクトまたはにバインドされているストレージの受信を終了しました。 `szStatusText`データの場所の表示名を提供します。  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 バインドされているオブジェクトのインスタンスが作成されるだけです。 `szStatusText`必要な場合は、クライアント、bind 操作を取り消す機会を許可する文字列の形式で、新しいオブジェクトの CLSID を提供します。  
  
##  <a name="onstartbinding"></a>  CAsyncMonikerFile::OnStartBinding  
 バインドが開始されるときに、アクションを実行する派生クラスでは、この関数をオーバーライドします。  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>コメント  
 この関数がモニカーによってコールバックされます。 既定の実装では、何も行われません。  
  
##  <a name="onstopbinding"></a>  CAsyncMonikerFile::OnStopBinding  
 モニカー バインド操作の最後にによって呼び出されます。  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>パラメーター  
 `hresult`  
 `HRESULT`つまりエラーまたは警告の値。  
  
 *szErrort*  
 エラーを説明する文字列を返します。  
  
### <a name="remarks"></a>コメント  
 転送が停止したときにアクションを実行するには、この関数をオーバーライドします。 既定では、解放`IBinding`です。  
  
 詳細については、`IBinding`インターフェイスでは、Windows SDK を参照してください。  
  
##  <a name="open"></a>  CAsyncMonikerFile::Open  
 非同期的にファイルを開くには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszURL`  
 非同期的に開かれるファイルへのポインター。 ファイルは、有効な URL またはファイル名にすることはできます。  
  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
 `pMoniker`  
 非同期モニカー インターフェイスへのポインター `IMoniker`、正確なモニカーで取得できる、ドキュメントのモニカーの組み合わせである**IOleClientSite::GetMoniker (** *OLEWHICHMK_コンテナー* **)**、およびパス名から作成されたモニカーです。 コントロールは、このモニカーを使用してをバインドすることができますが、これは、コントロールを保存する必要がありますモニカーではありません。  
  
 *pBindHost*  
 ポインター、`IBindHost`可能性のある相対パス名からモニカーを作成するために使用するインターフェイスです。 バインド ホストは、正しくないか、モニカーは提供されない場合、は、呼び出し既定**開く (** `lpszFileName` **、**`pError`**)** です。 詳細については、`IBindHost`インターフェイスでは、Windows SDK を参照してください。  
  
 `pServiceProvider`  
 `IServiceProvider` インターフェイスへのポインター。 サービス プロバイダーが正しくないか、サービスを提供する失敗したかどうかは`IBindHost`、呼び出しの既定値は**開く (** `lpszFileName` **、**`pError`**)** です。  
  
 *pUnknown*  
 ポインター、 **IUnknown**インターフェイスです。 場合`IServiceProvider`が見つかると、関数を検索するクエリ`IBindHost`です。 サービス プロバイダーが正しくないか、サービスを提供する失敗したかどうかは`IBindHost`、呼び出しの既定値は**開く (** `lpszFileName` **、**`pError`**)** です。  
  
### <a name="return-value"></a>戻り値  
 ファイルが正常に開かれている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この呼び出しでは、バインディング プロセスを開始します。  
  
 URL またはのファイル名を使用することができます、`lpszURL`パラメーター。 例えば:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 - または  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CMonikerFile クラス](../../mfc/reference/cmonikerfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMonikerFile クラス](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty クラス](../../mfc/reference/cdatapathproperty-class.md)
