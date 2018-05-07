---
title: CFileFind クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf77a5581dd9e8c9181c61287b6032f700d7d64b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cfilefind-class"></a>CFileFind クラス
基本クラスにはローカル ファイルの検索を実行し、 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)と[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)、インターネット ファイル検索を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|`CFileFind` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileFind::Close](#close)|検索要求を閉じます。|  
|[CFileFind::FindFile](#findfile)|指定したファイル名用のディレクトリを検索します。|  
|[CFileFind::FindNextFile](#findnextfile)|以前の呼び出しからファイル検索を続行[FindFile](#findfile)です。|  
|[CFileFind::GetCreationTime](#getcreationtime)|ファイルが作成された日時を取得します。|  
|[CFileFind::GetFileName](#getfilename)|見つかったファイルの拡張子を含む、名前を取得します。|  
|[CFileFind::GetFilePath](#getfilepath)|見つかったファイルの完全パスを取得します。|  
|[CFileFind::GetFileTitle](#getfiletitle)|見つかったファイルのタイトルを取得します。 タイトルには、拡張機能は含まれません。|  
|[CFileFind::GetFileURL](#getfileurl)|見つかったファイルのファイル パスを含む URL を取得します。|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|ファイルが最後にアクセスする時間を取得します。|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|ファイルが最後に変更が、保存時間を取得します。|  
|[CFileFind::GetLength](#getlength)|(バイト単位)、見つかったファイルの長さを取得します。|  
|[CFileFind::GetRoot](#getroot)|見つかったファイルのルート ディレクトリを取得します。|  
|[CFileFind::IsArchived](#isarchived)|見つかったファイルがアーカイブを決定します。|  
|[CFileFind::IsCompressed](#iscompressed)|見つかったファイルが圧縮されているかどうかを判断します。|  
|[CFileFind::IsDirectory](#isdirectory)|見つかったファイルがディレクトリであるかどうかを判断します。|  
|[CFileFind::IsDots](#isdots)|かどうかを見つかったファイルの名前、名前"です。"または".."、ディレクトリに実際には、ことを示します。|  
|[CFileFind::IsHidden](#ishidden)|かどうか、見つかったファイルが非表示を決定します。|  
|[CFileFind::IsNormal](#isnormal)|見つかったファイルが正常かどうかを (つまりが含まれない他の属性)。|  
|[CFileFind::IsReadOnly](#isreadonly)|見つかったファイルが読み取り専用のかどうかを判断します。|  
|[CFileFind::IsSystem](#issystem)|見つかったファイルがシステム ファイルであるかどうかを判断します。|  
|[CFileFind::IsTemporary](#istemporary)|見つかったファイルが一時的なかどうかを判断します。|  
|[CFileFind::MatchesMask](#matchesmask)|検索するファイルの目的のファイル属性を示します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|現在の検索のハンドルで指定されたファイルを閉じます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|ポインター、`CAtlTransactionManager`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CFileFind` 検索を開始し、ファイルを特定し、タイトル、名、またはファイルのパスを返すメンバー関数が含まれます。 インターネット検索では、このメンバー関数は[GetFileURL](#getfileurl)ファイルの URL を返します。  
  
 `CFileFind` その他の 2 つの MFC クラスの基底クラスは特定のサーバーの種類を検索するように設計: `CGopherFileFind` gopher サーバー固有の動作と`CFtpFileFind`具体的には FTP サーバーと連携します。 同時に、これら 3 つのクラスは、ファイルを検索する、サーバー プロトコル、ファイルの種類または場所に関係なく、ローカル コンピューターまたはリモート サーバー上のクライアントのシームレスなメカニズムを提供します。  
  
 次のコードは、各ファイルの名前を出力、現在のディレクトリ内のすべてのファイルに列挙されます。  
  
 [!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 このコードを例をシンプルにするには、C++ 標準ライブラリを使用して`cout`クラスです。 `cout`への呼び出しに行を置き換えることが`CListBox::AddString`、たとえば、グラフィカル ユーザー インターフェイスを持つプログラムでします。  
  
 使用する方法の詳細についての`CFileFind`し、その他の WinInet クラスは、記事を参照して[wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cfilefind"></a>  CFileFind::CFileFind  
 このメンバー関数が呼び出されます、`CFileFind`オブジェクトを構築します。  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetFileName](#getfilename)です。  
  
##  <a name="close"></a>  CFileFind::Close  
 検索を終了し、コンテキストをリセットし、すべてのリソースを解放するには、このメンバー関数を呼び出します。  
  
```  
void Close();
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後**閉じる**、新規作成する必要はありません`CFileFind`呼び出す前にインスタンス[FindFile](#findfile)新しい検索を開始します。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetFileName](#getfilename)です。  
  
##  <a name="closecontext"></a>  CFileFind::CloseContext  
 現在の検索のハンドルで指定されたファイルを閉じます。  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>コメント  
 検索のハンドルの現在の値で指定されたファイルを閉じます。 既定の動作を変更するには、この関数をオーバーライドします。  
  
 呼び出す必要があります、 [FindFile](#findfile)または[FindNextFile](#findnextfile)有効な検索のハンドルを取得するには、少なくとも 1 回の関数。 **FindFile**と`FindNextFile`関数は、指定した名前に一致する名前を持つファイルを検索する検索のハンドルを使用します。  
  
##  <a name="findfile"></a>  CFileFind::FindFile  
 ファイル検索を開始するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrName`  
 検索するファイルの名前を含む文字列へのポインター。 渡す場合**NULL**の`pstrName`、 **FindFile**は、ワイルドカード (\*.\*) 検索します。  
  
 *dwUnused*  
 予約する**FindFile**派生クラス。 0 にする必要があります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得する Win32 関数を呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。  
  
### <a name="remarks"></a>コメント  
 呼び出した後**FindFile**ファイル検索を開始する[FindNextFile](#findnextfile)を後続のファイルを取得します。 呼び出す必要があります`FindNextFile`を少なくとも 1 回を呼び出す前に、次の属性のメンバー関数。  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::IsDirectory](#isdirectory)です。  
  
##  <a name="findnextfile"></a>  CFileFind::FindNextFile  
 以前の呼び出しからファイル検索を続行するには、このメンバー関数を呼び出す[FindFile](#findfile)です。  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>戻り値  
 多くのファイルがある場合は 0 以外。見つかったファイルがディレクトリに最後の 1 つである場合、またはエラーが発生した場合は 0 します。 拡張エラー情報を取得する Win32 関数を呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。 見つかったファイルがディレクトリに最後のファイルまたは一致するファイルが見つからないことができる場合、 `GetLastError` ERROR_NO_MORE_FILES を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります`FindNextFile`を少なくとも 1 回を呼び出す前に、次の属性のメンバー関数。  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile` Win32 関数をラップ[FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428)です。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::IsDirectory](#isdirectory)です。  
  
##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime  
 指定したファイルが作成された時刻を取得するには、このメンバー関数を呼び出します。  
  
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
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetCreationTime` 場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されました`CFileFind`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetCreationTime`です。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される時刻スタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の形式に関する情報。 オペレーティング システムによってはローカル タイム ゾーンをマシンに、ファイルがあるの時刻が返されることがあります。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API 詳細についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="getfilename"></a>  CFileFind::GetFileName  
 見つかったファイルの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最後に見つかったファイルの名前。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile) GetFileName を呼び出す前に少なくとも 1 回です。  
  
 `GetFileName` 3 つの 1 つ`CFileFind`をいくつかの形式のファイル名を返すメンバー関数。 次の一覧には、3 つと、その違いについて説明します。  
  
- `GetFileName` 拡張子を含む、ファイル名を返します。 たとえば、呼び出す`GetFileName`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル名を返します`myfile.txt`です。  
  
- [まで含めた](#getfilepath)全体、ファイルのパスを返します。 たとえば、呼び出す`GetFilePath`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル パスを返します`c:\myhtml\myfile.txt`です。  
  
- [GetFileTitle](#getfiletitle)ファイル拡張子を除く、ファイル名を返します。 たとえば、呼び出す`GetFileTitle`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイルのタイトルを返します`myfile`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>  CFileFind::GetFilePath  
 指定されたファイルの完全なパスを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 指定されたファイルのパスです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetFilePath`です。  
  
 `GetFilePath` 3 つの 1 つ`CFileFind`をいくつかの形式のファイル名を返すメンバー関数。 次の一覧には、3 つと、その違いについて説明します。  
  
- [GetFileName](#getfilename)拡張子を含む、ファイル名を返します。 たとえば、呼び出す`GetFileName`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル名を返します`myfile.txt`です。  
  
- `GetFilePath` ファイルの完全なパスを返します。 たとえば、呼び出す`GetFilePath`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル パスを返します`c:\myhtml\myfile.txt`です。  
  
- [GetFileTitle](#getfiletitle)ファイル拡張子を除く、ファイル名を返します。 たとえば、呼び出す`GetFileTitle`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイルのタイトルを返します`myfile`です。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetFileName](#getfilename)です。  
  
##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle  
 見つかったファイルのタイトルを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルのタイトル。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetFileTitle`です。  
  
 `GetFileTitle` 3 つの 1 つ`CFileFind`をいくつかの形式のファイル名を返すメンバー関数。 次の一覧には、3 つと、その違いについて説明します。  
  
- [GetFileName](#getfilename)拡張子を含む、ファイル名を返します。 たとえば、呼び出す`GetFileName`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル名を返します`myfile.txt`です。  
  
- [まで含めた](#getfilepath)全体、ファイルのパスを返します。 たとえば、呼び出す`GetFilePath`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイル パスを返します`c:\myhtml\myfile.txt`です。  
  
- `GetFileTitle` ファイル拡張子を除く、ファイル名を返します。 たとえば、呼び出す`GetFileTitle`ファイルに関するユーザー メッセージを生成する`c:\myhtml\myfile.txt`ファイルのタイトルを返します`myfile`です。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetFileName](#getfilename)です。  
  
##  <a name="getfileurl"></a>  CFileFind::GetFileURL  
 指定された URL を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 完全な URL。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetFileURL`です。  
  
 `GetFileURL` このメンバー関数に似ています[まで含めた](#getfilepath)形式で URL を返します点を除き、`file://path`です。 たとえば、呼び出す`GetFileURL`の完全な URL を取得する`myfile.txt`URL を返します`file://c:\myhtml\myfile.txt`です。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetFileName](#getfilename)です。  
  
##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime  
 指定したファイルの最終アクセス時刻を取得するには、このメンバー関数を呼び出します。  
  
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
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetLastAccessTime` 場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されました`CFileFind`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetLastAccessTime`です。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される時刻スタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の形式に関する情報。 オペレーティング システムによってはローカル タイム ゾーンをマシンに、ファイルがあるの時刻が返されることがあります。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API 詳細についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime  
 最後に、ファイルが変更された時刻を取得するには、このメンバー関数を呼び出します。  
  
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
 成功した場合は 0 以外。それ以外の場合は 0 を返します。 `GetLastWriteTime` 場合にのみ、0 を返します[FindNextFile](#findnextfile)は決してこので呼び出されました`CFileFind`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetLastWriteTime`です。  
  
> [!NOTE]
>  すべてのファイル システムでは、同じセマンティクスを使用して、この関数によって返される時刻スタンプを実装します。 この関数は、基になるファイル システムまたはサーバーがサポートしない場合、時間属性を維持するその他のタイム スタンプ関数によって返される同じ値を返す可能性があります。 参照してください、 [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造での時刻の形式に関する情報。 オペレーティング システムによってはローカル タイム ゾーンをマシンに、ファイルがあるの時刻が返されることがあります。 Win32 を参照してください[詳細](http://msdn.microsoft.com/library/windows/desktop/ms724277)API 詳細についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="getlength"></a>  CFileFind::GetLength  
 このメンバー関数 (バイト単位)、見つかったファイルの長さを取得します。  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (バイト単位)、見つかったファイルの長さ。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetLength`です。  
  
 `GetLength` Win32 構造を使用して[WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)を取得し、ファイル サイズの値をバイト単位で取得します。  
  
> [!NOTE]
>  MFC 7.0 以降`GetLength`64 ビット整数型をサポートしています。 以前この新しいバージョンのライブラリでビルドされた既存のコードについては、切り捨ての警告があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>  CFileFind::GetRoot  
 見つかったファイルのルートを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アクティブな検索のルートです。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`GetRoot`です。  
  
 このメンバー関数は、ドライブ指定子と検索を開始するために使用するパス名を返します。 たとえば、呼び出し[FindFile](#findfile)で`*.dat`で結果`GetRoot`空の文字列を返します。 など、パスを渡す`c:\windows\system\*.dll`を**FindFile**結果`GetRoot`返す`c:\windows\system\`です。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetFileName](#getfilename)です。  
  
##  <a name="isarchived"></a>  CFileFind::IsArchived  
 見つかったファイルがアーカイブを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションがバックアップまたは FILE_ATTRIBUTE_ARCHIVE で識別されるファイル属性で、削除するのには、アーカイブ ファイルをマーク、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsArchived`です。  
  
 このメンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="iscompressed"></a>  CFileFind::IsCompressed  
 見つかったファイルが圧縮されているかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 圧縮されたファイルが FILE_ATTRIBUTE_COMPRESSED でマークされたでファイル属性が識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 ファイルの場合は、この属性は、すべてのファイルにデータが圧縮されているを示します。 ディレクトリの場合は、この属性は、圧縮が新しく作成されたファイルとサブディレクトリの既定値を示します。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsCompressed`です。  
  
 このメンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="isdirectory"></a>  CFileFind::IsDirectory  
 見つかったファイルがディレクトリであるかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ディレクトリであるファイルが FILE_ATTRIBUTE_DIRECTORY で識別されるファイル属性でマークされた、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsDirectory`です。  
  
 このメンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてはします。  
  
### <a name="example"></a>例  
 この小さなプログラムは、再帰の回数が、C:\ ドライブのすべてのディレクトリをディレクトリの名前を出力します。  
  
 [!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>  CFileFind::IsDots  
 ファイルを反復処理するときに現在のディレクトリとその親ディレクトリのマーカーをテストするには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>戻り値  
 見つかったファイルの名前にする場合は 0 以外"です。"または".."、見つかったファイルがディレクトリでは実際にします。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsDots`です。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::IsDirectory](#isdirectory)です。  
  
##  <a name="ishidden"></a>  CFileFind::IsHidden  
 かどうか、見つかったファイルが非表示を決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 付いている FILE_ATTRIBUTE_HIDDEN、非表示のファイルのファイル属性が識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 隠しファイルは通常のディレクトリ一覧に含まれていません。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsHidden`です。  
  
 このメンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="isnormal"></a>  CFileFind::IsNormal  
 見つかったファイルが通常のファイルであるかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 FILE_ATTRIBUTE_NORMAL でマークされたファイル、ファイル属性の識別、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 通常のファイルには、他の属性セットがありません。 その他のすべてのファイル属性は、この属性をオーバーライドします。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsNormal`です。  
  
 このメンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="isreadonly"></a>  CFileFind::IsReadOnly  
 このメンバー関数、見つかったファイルが読み取り専用であるかどうかを呼び出します。  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 読み取り専用ファイルが FILE_ATTRIBUTE_READONLY でマークされたでファイル属性が識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 アプリケーションは、このようなファイルを読み取ることができますが、それへの書き込みや削除もできません。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsReadOnly`です。  
  
 このメンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="issystem"></a>  CFileFind::IsSystem  
 見つかったファイルがシステム ファイルであるかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 システム ファイルが FILE_ATTRIBUTE_SYSTEM でマークされたでファイル属性が識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 システム ファイルはの一部であるまたは排他的、オペレーティング システムによって使用されます。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsSystem`です。  
  
 このメンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="istemporary"></a>  CFileFind::IsTemporary  
 見つかったファイルが一時ファイルを確認するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 一時ファイルが FILE_ATTRIBUTE_TEMPORARY でマークされたでファイル属性が識別される、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)構造体。 一時ファイルは、一時的な記憶域に使用されます。 アプリケーションは、絶対に必要な場合にのみ、ファイルに書き込む必要があります。 ファイルのデータの大部分は、ファイルがすぐに削除されるため、メディアに書き込まれずに、メモリに残ります。  
  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`IsTemporary`です。  
  
 このメンバー関数を参照してください[は](#matchesmask)ファイル属性の完全な一覧についてはします。  
  
### <a name="example"></a>例  
  例を参照して[CFileFind::GetLength](#getlength)です。  
  
##  <a name="m_ptm"></a>  CFileFind::m_pTM  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="matchesmask"></a>  CFileFind::MatchesMask  
 見つかったファイルのファイル属性をテストするには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMask`  
 識別される 1 つまたは複数のファイル属性を指定します、 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)見つかったファイルの構造体。 複数の属性を検索するには、ビットごとの OR を使用して (&#124;) 演算子。 次の属性の任意の組み合わせも許容されます。  
  
-   FILE_ATTRIBUTE_ARCHIVE ファイルは、アーカイブ ファイルです。 アプリケーションでは、この属性を使用して、ファイルをバックアップまたは削除としてマークします。  
  
-   FILE_ATTRIBUTE_COMPRESSED ファイルまたはディレクトリが圧縮されます。 ファイルのすべてのファイルにデータが圧縮されていることを意味します。 ディレクトリの圧縮が新しく作成されたファイルとサブディレクトリの既定値であることを意味します。  
  
-   FILE_ATTRIBUTE_DIRECTORY ファイルは、ディレクトリです。  
  
-   FILE_ATTRIBUTE_NORMAL ファイルには、他の属性セットがありません。 この属性は、単独で使用される場合にのみ有効です。 その他のすべてのファイル属性は、この属性をオーバーライドします。  
  
-   FILE_ATTRIBUTE_HIDDEN ファイルは表示されません。 通常のディレクトリ一覧に含めることは。  
  
-   FILE_ATTRIBUTE_READONLY ファイルは読み取り専用です。 アプリケーションできますファイルの読み取りことはできませんへの書き込みまたは削除。  
  
-   FILE_ATTRIBUTE_SYSTEM ファイルの一部であるか、オペレーティング システムのみで使用します。  
  
-   FILE_ATTRIBUTE_TEMPORARY ファイルは、一時的なストレージの使用されています。 アプリケーションは、絶対に必要な場合にのみ、ファイルに書き込む必要があります。 ファイルのデータの大部分は、ファイルがすぐに削除されるため、メディアに書き込まれずに、メモリに残ります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 拡張エラー情報を取得する Win32 関数を呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[FindNextFile](#findnextfile)呼び出す前に少なくとも 1 回`MatchesMask`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind クラス](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile クラス](../../mfc/reference/chttpfile-class.md)
