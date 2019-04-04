---
title: CAsyncMonikerFile クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: b86cba0c2e8f7991902a552d404355d6c1474138
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425823"
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
|[CAsyncMonikerFile::Close](#close)|終了し、すべてのリソースを解放します。|
|[CAsyncMonikerFile::GetBinding](#getbinding)|バインドの非同期転送へのポインターを取得します。|
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|ストリーム内のデータの形式を取得します。|
|[CAsyncMonikerFile::Open](#open)|非同期的にファイルを開きます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|実装する COM オブジェクトを作成します。`IBindStatusCallback`します。|
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|OLE システム ライブラリを作成するバインドの種類に関する情報を要求によって呼び出されます。|
|[CAsyncMonikerFile::GetPriority](#getpriority)|バインディングの優先順位を取得する OLE システム ライブラリによって呼び出されます。|
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|非同期バインド操作中に、クライアントに利用可能になったデータを提供すると呼ばれます。|
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|リソースが少ないときに呼び出されます。|
|[CAsyncMonikerFile::OnProgress](#onprogress)|データのダウンロード処理の進行状況を示すために呼び出されます。|
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|バインドが開始されるときに呼び出されます。|
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|非同期転送が停止したときに呼び出されます。|

## <a name="remarks"></a>Remarks

派生した[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)、さらにから派生する[COleStreamFile](../../mfc/reference/colestreamfile-class.md)、`CAsyncMonikerFile`を使用して、 [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)インターフェイスを任意のデータ ストリームにアクセスするにはURL から非同期的にファイルの読み込みを含む、非同期的にします。 ファイルは、ActiveX コントロールのデータパス プロパティであることができます。

非同期モニカーは、ファイル転送中に、応答性の高いユーザー インターフェイスを提供するインターネット対応のアプリケーションと ActiveX コントロールで主に使用されます。 これの典型的な例の使用は、 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) ActiveX コントロールの非同期のプロパティを提供します。 `CDataPathProperty`オブジェクトは、時間のかかるプロパティ exchange プロセス中に新しいデータの可用性を通知するコールバックを順次取得します。

インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次の記事を参照してください。

- [インターネット最初のステップ:非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)

- [インターネット最初のステップ:ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

##  <a name="casyncmonikerfile"></a>  CAsyncMonikerFile::CAsyncMonikerFile

`CAsyncMonikerFile` オブジェクトを構築します。

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>Remarks

作成されません、`IBindHost`インターフェイス。 `IBindHost` 指定した場合にのみ使用されます、`Open`メンバー関数。

説明については、`IBindHost`インターフェイス、Windows SDK を参照してください。

##  <a name="close"></a>  CAsyncMonikerFile::Close

この関数では、閉じ、すべてのリソースを解放します。

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

開かれていない、または既に閉じられているファイルを呼び出すことができます。

##  <a name="createbindstatuscallback"></a>  CAsyncMonikerFile::CreateBindStatusCallback

実装する COM オブジェクトを作成します。`IBindStatusCallback`します。

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>パラメーター

*pUnkControlling*<br/>
制御の不明なへのポインター (外部`IUnknown`) 集計が使用されていない場合は null です。

### <a name="return-value"></a>戻り値

場合*pUnkControlling*が NULL でない関数の内部にポインターを返します`IUnknown`新しい COM オブジェクト サポート`IBindStatusCallback`します。 場合`pUnkControlling`が null の場合、関数へのポインターを返します、`IUnknown`新しい COM オブジェクト サポート`IBindStatusCallback`します。

### <a name="remarks"></a>Remarks

`CAsyncMonikerFile` 実装する COM オブジェクトが必要です`IBindStatusCallback`します。 MFC は、このようなオブジェクトを実装しが集計されます。 オーバーライドできます`CreateBindStatusCallback`独自の COM オブジェクトを返します。 呼び出すことによって、COM オブジェクトが MFC の実装を集計できる`CreateBindStatusCallback`COM オブジェクトの制御不明。 使用して実装されている COM オブジェクト、 `CCmdTarget` COM サポートを制御する不明なを使用して、取得できます`CCmdTarget::GetControllingUnknown`します。

COM オブジェクトを呼び出すことで MFC の実装に委任できますまたは、`CreateBindStatusCallback( NULL )`します。

[CAsyncMonikerFile::Open](#open)呼び出し`CreateBindStatusCallback`します。

非同期モニカーと非同期のバインドの詳細については、、 [IBindStatusCallback](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775060\(v=vs.85\))インターフェイスと[非同期バインド方法およびストレージ作業](/windows/desktop/Stg/how-asynchronous-binding-and-storage-work)を参照してください。 集計の詳細については、[集計](/windows/desktop/com/aggregation)を参照してください。 3 つすべてのトピックは、Windows SDK には。

##  <a name="getbindinfo"></a>  CAsyncMonikerFile::GetBindInfo

非同期モニカーをバインドする方法を指示する非同期モニカーのクライアントから呼び出されます。

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>戻り値

設定を取得します`IBindStatusCallBack`します。 説明については、`IBindStatusCallback`インターフェイス、Windows SDK を参照してください。

### <a name="remarks"></a>Remarks

既定の実装では、ストレージ メディア (ストリーム) を使用して、データ プッシュ モデルを使用して、非同期へのバインドを設定します。 バインドの動作を変更したい場合は、この関数をオーバーライドします。

これを行う理由の 1 つは、データ プッシュ モデルではなくデータ プル モデルを使用してバインドすることです。 データ プル モデルでは、クライアントが、バインド操作をドライブし、モニカーが読み取られるときに、クライアントにデータがのみ提供します。 データ プッシュ モデルでは、モニカーは、バインドの非同期操作し、継続的に新しいデータがあるたびにクライアントに通知します。

##  <a name="getbinding"></a>  CAsyncMonikerFile::GetBinding

バインドの非同期転送へのポインターを取得するには、この関数を呼び出します。

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>戻り値

ポインター、`IBinding`非同期転送の開始時に提供されるインターフェイス。 何らかの理由により、転送の場合、NULL を返しますは非同期で行われることはできません。

### <a name="remarks"></a>Remarks

これにより、データ転送プロセスを制御する、`IBinding`インターフェイスなどの`IBinding::Abort`、 `IBinding::Pause`、および`IBinding::Resume`します。

説明については、`IBinding`インターフェイス、Windows SDK を参照してください。

##  <a name="getformatetc"></a>  CAsyncMonikerFile::GetFormatEtc

ストリーム内のデータの形式を取得するには、この関数を呼び出します。

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>戻り値

Windows 構造体へのポインター [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)現在開いているストリーム。 モニカーがバインドされていない場合、非同期でない場合、または非同期操作が開始されていない場合は、NULL を返します。

##  <a name="getpriority"></a>  CAsyncMonikerFile::GetPriority

バインディング操作のスレッドに優先順位を受信するバインディング プロセスを開始すると非同期モニカーのクライアントから呼び出されます。

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>戻り値

優先順位が非同期転送が実行されます。 標準スレッドの優先順位フラグのいずれか:THREAD_PRIORITY_ABOVE_NORMAL、THREAD_PRIORITY_BELOW_NORMAL、THREAD_PRIORITY_HIGHEST、THREAD_PRIORITY_IDLE、THREAD_PRIORITY_LOWEST、THREAD_PRIORITY_NORMAL、および THREAD_PRIORITY_TIME_CRITICAL します。 Windows 関数を参照してください。 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority)のこれらの値の説明。

### <a name="remarks"></a>Remarks

`GetPriority` 呼び出さないで直接します。 THREAD_PRIORITY_NORMAL は、既定の実装によって返されます。

##  <a name="ondataavailable"></a>  CAsyncMonikerFile::OnDataAvailable

非同期モニカーを呼び出す`OnDataAvailable`クライアントにデータを提供できるよう、非同期の中に、バインド操作。

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>パラメーター

*dwSize*<br/>
バインディングの当初から使用可能なデータのバイト単位で累積時間。 データの量が、操作に関連するではないこと、または特定の量が利用できないことを示す、0 にすることができます。

*bscfFlag*<br/>
BSCF 列挙値。 次の値の 1 つ以上を指定できます。

- BSCF_FIRSTDATANOTIFICATION 最初の呼び出しを識別する`OnDataAvailable`操作が指定したバインド。

- BSCF_INTERMEDIATEDATANOTIFICATION への中間の呼び出しを識別する`OnDataAvailable`バインド操作。

- 知らせる最後の呼び出しを識別する`OnDataAvailable`バインド操作。

### <a name="remarks"></a>Remarks

この関数の既定の実装は、何も行いません。 実装のサンプルについては、次の例を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

##  <a name="onlowresource"></a>  CAsyncMonikerFile::OnLowResource

リソースが少ないときに、モニカーによって呼び出されます。

```
virtual void OnLowResource();
```

### <a name="remarks"></a>Remarks

既定の実装`GetBinding( )-> Abort( )`します。

##  <a name="onprogress"></a>  CAsyncMonikerFile::OnProgress

通常は、時間のかかる操作中に適切な間隔でこのバインド操作の現在の進行状況を示すために繰り返しモニカーによって呼び出されます。

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>パラメーター

*ulProgress*<br/>
示される予想される最大値を基準としたバインド操作の現在の進行状況を示す*ulProgressMax*します。

*ulProgressMax*<br/>
予想される最大値を示す*ulProgress*呼び出しの期間の`OnProgress`この操作にします。

*ulStatusCode*<br/>
バインド操作の進行状況に関する追加情報を提供します。 有効な値から取得されます、`BINDSTATUS`列挙体。 使用可能な値は、「解説」を参照してください。

*szStatusText*<br/>
値に応じて、現在の進行状況に関する情報*ulStatusCode*します。 使用可能な値は、「解説」を参照してください。

### <a name="remarks"></a>Remarks

指定できる値*ulStatusCode* (および*szStatusText*値ごとに) は。

|||
|-|-|
|BINDSTATUS_FINDINGRESOURCE  |バインド操作では、オブジェクトにバインドされている記憶域を含むリソースを見つけることです。 *SzStatusText*検索対象のリソースの表示名を提供します (たとえば、"www.microsoft.com") にします。  |
|BINDSTATUS_CONNECTING  |オブジェクトにバインドされている記憶域を含むリソースへのバインド操作です。 *SzStatusText* (たとえば、IP アドレス) に接続されているリソースの表示名を提供します。  |
|BINDSTATUS_SENDINGREQUEST|バインド操作は、オブジェクトまたはバインドされているストレージに要求しています。 *SzStatusText*オブジェクト (たとえば、ファイル名) の表示名を提供します。|
|BINDSTATUS_REDIRECTING  |バインド操作は別のデータの場所にリダイレクトされました。 *SzStatusText*新しいデータの場所の表示名を提供します。  |
|BINDSTATUS_USINGCACHEDCOPY  |バインド操作には、要求されたオブジェクトまたは記憶域キャッシュされたコピーから取得しています。 *SzStatusText*は NULL です。  |
|BINDSTATUS_BEGINDOWNLOADDATA  |バインド操作では、オブジェクトまたはバインドされているストレージの受信を開始しました。 *SzStatusText*データの場所の表示名を提供します。|
|BINDSTATUS_DOWNLOADINGDATA  |バインド操作にバインドされている記憶域、オブジェクトを受信し続けます。 *SzStatusText*データの場所の表示名を提供します。  |
|BINDSTATUS_ENDDOWNLOADDATA  |バインド操作では、オブジェクトまたはバインドされているストレージの受信を終了しました。 *SzStatusText*データの場所の表示名を提供します。  |
|BINDSTATUS_CLASSIDAVAILABLE  |バインドされているオブジェクトのインスタンスが作成されるだけです。 *SzStatusText*必要な場合は、クライアント、バインド操作をキャンセルする機会を許可する文字列の形式で、新しいオブジェクトの CLSID を提供します。  |

##  <a name="onstartbinding"></a>  CAsyncMonikerFile::OnStartBinding

バインドを開始するときにアクションを実行する派生クラスでは、この関数をオーバーライドします。

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>Remarks

この関数が、モニカーによってコールバックされます。 既定の実装では、何も行われません。

##  <a name="onstopbinding"></a>  CAsyncMonikerFile::OnStopBinding

バインド操作の最後に、モニカーによって呼び出されます。

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>パラメーター

*hresult*<br/>
エラーまたは警告の値の HRESULT です。

*szErrort*<br/>
エラーを説明する文字列。

### <a name="remarks"></a>Remarks

転送が停止したときにアクションを実行するには、この関数をオーバーライドします。 既定では、解放`IBinding`します。

説明については、`IBinding`インターフェイス、Windows SDK を参照してください。

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

*lpszURL*<br/>
非同期的に開かれるファイルへのポインター。 有効な URL またはファイル名、ファイルができます。

*pError*<br/>
ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。

*pMoniker*<br/>
非同期モニカー インターフェイスへのポインター`IMoniker`で取得できる、ドキュメントのモニカーの組み合わせである正確なモニカー `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`、およびパス名から作成されたモニカー。 コントロールがバインドする、このモニカーを使用できますが、これは、コントロールを保存する必要がありますモニカーではありません。

*pBindHost*<br/>
ポインター、`IBindHost`可能性のある相対的なパス名からモニカーを作成するために使用するインターフェイス。 バインドのホストが無効であるか、モニカーは行わない、する場合は、呼び出し既定`Open(lpszFileName,pError)`します。 説明については、`IBindHost`インターフェイス、Windows SDK を参照してください。

*pServiceProvider*<br/>
`IServiceProvider` インターフェイスへのポインター。 サービス プロバイダーが正しくないか、またはサービスを提供するが失敗したかどうかは`IBindHost`、呼び出しが既定で`Open(lpszFileName,pError)`します。

*pUnknown*<br/>
`IUnknown` インターフェイスへのポインター。 場合`IServiceProvider`が見つかると、関数を検索するクエリ`IBindHost`します。 サービス プロバイダーが正しくないか、またはサービスを提供するが失敗したかどうかは`IBindHost`、呼び出しが既定で`Open(lpszFileName,pError)`します。

### <a name="return-value"></a>戻り値

ファイルが正常に開かれている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この呼び出しは、バインディング プロセスを開始します。

URL またはファイルの名前を使用することができます、 *lpszURL*パラメーター。 例:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- または -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>関連項目

[CMonikerFile クラス](../../mfc/reference/cmonikerfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CMonikerFile クラス](../../mfc/reference/cmonikerfile-class.md)<br/>
[CDataPathProperty クラス](../../mfc/reference/cdatapathproperty-class.md)
