---
title: CGopherFileFind クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
dev_langs:
- C++
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 584644963a647c5b458407b2d777f91014b40fad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369415"
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind クラス
gopher サーバーのインターネット ファイル検索を支援します。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`し、Windows XP のプラットフォームでは機能しませんが、引き続き以前のプラットフォームで動作するため、そのメンバーが使用されなくなりました。  
  
## <a name="syntax"></a>構文  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|`CGopherFileFind` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherFileFind::FindFile](#findfile)|Gopher サーバー上のファイルを検索します。|  
|[CGopherFileFind::FindNextFile](#findnextfile)|以前の呼び出しからファイル検索を続行[FindFile](#findfile)です。|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|指定したファイルが作成された日時を取得します。|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|指定したファイルの最終アクセス時間を取得します。|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|指定したファイルに最後に書き込んだ時間を取得します。|  
|[CGopherFileFind::GetLength](#getlength)|(バイト単位)、見つかったファイルの長さを取得します。|  
|[なった](#getlocator)|取得、`CGopherLocator`オブジェクト。|  
|[CGopherFileFind::GetScreenName](#getscreenname)|Gopher 画面の名前を取得します。|  
|[CGopherFileFind::IsDots](#isdots)|ファイルを反復処理するときに現在ディレクトリとその親ディレクトリのマーカーをテストします。|  
  
## <a name="remarks"></a>コメント  
 `CGopherFileFind` 検索を開始、ファイルを検索し、ファイルの URL を返すメンバー関数が含まれます。  
  
 インターネットとローカル ファイルの検索を含めるために設計されて他の MFC クラス[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)と[CFileFind](../../mfc/reference/cfilefind-class.md)です。 と共に`CGopherFileFind`、これらのクラスは、サーバー プロトコル、ファイルの種類または場所 (ローカル コンピューターまたはリモート サーバーのいずれかです) に関係なく、特定のファイルを検索するユーザーのシームレスなメカニズムを提供。HTTP は検索に必要なファイルを直接操作をサポートしていないために、HTTP サーバーで検索するための MFC クラスがないことに注意してください。  
  
> [!NOTE]
> `CGopherFileFind` 基底クラスの次のメンバー関数をサポートしていません[CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 さらを使用すると`CGopherFileFind`、`CFileFind`メンバー関数は、 [IsDots](../../mfc/reference/cfilefind-class.md#isdots)は常に**FALSE**です。  
  
 使用する方法の詳細についての`CGopherFileFind`し、その他の WinInet クラスは、記事を参照して[wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind  
 このメンバー関数は構築するために、`CGopherFileFind`オブジェクト。  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pConnection`  
 ポインター、[関数](../../mfc/reference/cgopherconnection-class.md)オブジェクト。  
  
 `dwContext`  
 操作のコンテキストの識別子。 参照してください**解説**の詳細については`dwContext`します。  
  
### <a name="remarks"></a>コメント  
 既定値`dwContext`に MFC によって送信される、`CGopherFileFind`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CGopherFileFind`オブジェクト。 構築する場合、`CGopherFileFind`オブジェクトのコンテキスト識別子を独自の値に設定する既定値をオーバーライドすることができます。 コンテキスト識別子に返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)いる識別されるオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="findfile"></a>  CGopherFileFind::FindFile  
 Gopher ファイルを検索するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL FindFile(
    CGopherLocator& refLocator,  
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

 
virtual BOOL FindFile(
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>パラメーター  
 `refLocator`  
 参照、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
 *pstrString*  
 ファイル名を含む文字列へのポインター。  
  
 `dwFlags`  
 このセッションを処理する方法を示すフラグ。 有効なフラグは次のとおりです。  
  
-   ローカルにキャッシュされている場合でも、INTERNET_FLAG_RELOAD はリモート サーバーからデータを取得します。  
  
-   ローカルまたはすべてのゲートウェイには、データをキャッシュ INTERNET_FLAG_DONT_CACHE しません。  
  
-   セキュア ソケット レイヤーまたは割合で、ネットワーク上でのセキュリティで保護されたトランザクションの INTERNET_FLAG_SECURE 要求 このフラグは、HTTP 要求のみに適用します。  
  
-   INTERNET_FLAG_USE_EXISTING 可能な場合は、新しいサーバーに既存の接続を再利用**FindFile**要求、要求ごとに新しいセッションを作成する代わりにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得する Win32 関数を呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。  
  
### <a name="remarks"></a>コメント  
 呼び出した後**FindFile** gopher の最初のオブジェクトを取得するを呼び出すことができます[FindNextFile](#findnextfile)後続 gopher ファイルを取得します。  
  
##  <a name="findnextfile"></a>  CGopherFileFind::FindNextFile  
 呼び出しで開始されたファイルの検索を続行するには、このメンバー関数を呼び出す[CGopherFileFind::FindFile](#findfile)です。  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>戻り値  
 多くのファイルがある場合は 0 以外。見つかったファイルがディレクトリに最後の 1 つである場合、またはエラーが発生した場合は 0 します。 拡張エラー情報を取得する Win32 関数を呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。 見つかったファイルがディレクトリに最後のファイルまたは一致するファイルが見つからないことができる場合、 `GetLastError` ERROR_NO_MORE_FILES を返します。  
  
##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime  
 現在のファイルの作成時刻を取得します。  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pTimeStamp`  
 ポインター、 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)ファイルが作成された時刻を含む構造体。  
  
 `refTime`  
 参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetCreationTime` 場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されました`CGopherFileFind`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetCreationTime`です。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される時刻スタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の形式に関する情報。 一部のオペレーティング システムはローカル タイム ゾーンをマシンに、ファイルがあるの時刻が返されることがあります。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API 詳細についてはします。  
  
##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime  
 指定したファイルの最終アクセス時間を取得します。  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `refTime`  
 参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。  
  
 `pTimeStamp`  
 ポインター、 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)ファイルの最終アクセス時刻を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetLastAccessTime` 場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されました`CGopherFileFind`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetLastAccessTime`です。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される時刻スタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の形式に関する情報。 一部のオペレーティング システムはローカル タイム ゾーンをマシンに、ファイルがあるの時刻が返されることがあります。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API 詳細についてはします。  
  
##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime  
 ファイルが変更された最終時刻を取得します。  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pTimeStamp`  
 ポインター、 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)ファイルに最後に書き込んだ時間を含む構造体。  
  
 `refTime`  
 参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetLastWriteTime` 場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されました`CGopherFileFind`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetLastWriteTime`です。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される時刻スタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の形式に関する情報。 一部のオペレーティング システムはローカル タイム ゾーンをマシンに、ファイルがあるの時刻が返されることがあります。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API 詳細についてはします。  
  
##  <a name="getlength"></a>  CGopherFileFind::GetLength  
 見つかったファイルのバイト単位の長さを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 見つかったファイルの長さ、(バイト単位)。  
  
### <a name="remarks"></a>コメント  
 `GetLength` Win32 構造を使用して[WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)バイト単位で、ファイル サイズの値を取得します。  
  
> [!NOTE]
>  MFC 7.0 以降`GetLength`64 ビット整数型をサポートしています。 この新しいバージョンのライブラリでビルドされた既存のコードは、切り捨ての警告があります。  
  
### <a name="example"></a>例  
  例を参照して[結び付けてその中](../../mfc/reference/cfile-class.md#getlength)(基底クラスの実装)。  
  
##  <a name="getlocator"></a>  なった  
 取得するには、このメンバー関数を呼び出す、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクトを[FindFile](#findfile)を使用して、gopher ファイルを検索します。  
  
```  
CGopherLocator GetLocator() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `CGopherLocator` オブジェクト。  
  
##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName  
 Gopher 画面の名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetScreenName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Gopher 画面の名前。  
  
##  <a name="isdots"></a>  CGopherFileFind::IsDots  
 ファイルを反復処理するときに現在ディレクトリとその親ディレクトリのマーカーをテストします。  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>戻り値  
 見つかったファイルの名前にする場合は 0 以外"です。"または".."、見つかったファイルがディレクトリでは実際にします。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsDots`です。  
  
## <a name="see-also"></a>関連項目  
 [CFileFind クラス](../../mfc/reference/cfilefind-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind クラス](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind クラス](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile クラス](../../mfc/reference/chttpfile-class.md)
