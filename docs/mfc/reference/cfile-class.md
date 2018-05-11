---
title: CFile クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee4086b25fe675aaab1b484f21ec7e22e5603781
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cfile-class"></a>CFile クラス
ファイルに関する MFC の基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CFile : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ほか](#cfile)|構築、`CFile`パスまたはファイルのハンドルからのオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[解放](#abort)|すべての警告とエラーを無視するファイルを閉じます。|  
|[データ](#close)|ファイルを終了し、オブジェクトを削除します。|  
|[CFile::Duplicate](#duplicate)|このファイルに基づく重複するオブジェクトを構築します。|  
|[CFile::Flush](#flush)|まだが書き込まれるようにデータをフラッシュします。|  
|[CFile::GetFileName](#getfilename)|選択したファイルのファイル名を取得します。|  
|[CFile::GetFilePath](#getfilepath)|選択したファイルの完全ファイル パスを取得します。|  
|[CFile::GetFileTitle](#getfiletitle)|選択したファイルのタイトルを取得します。|  
|[結び付けてその中](#getlength)|ファイルの長さを取得します。|  
|[実行](#getposition)|現在のファイル ポインターを取得します。|  
|[Cfile::getstatus](#getstatus)|または、静的バージョンで、開いているファイルの状態を取得、指定されたファイル (静的、仮想関数) の状態を取得します。|  
|[CFile::LockRange](#lockrange)|ファイル内のバイトの範囲をロックします。|  
|[CFile::Open](#open)|安全なエラー テスト オプションを使用してファイルを開きます。|  
|[:Read](#read)|現在のファイル位置にあるファイルからの読み取り (バッファーなし) データ。|  
|[CFile::Remove](#remove)|指定されたファイル (静的関数) を削除します。|  
|[CFile::Rename](#rename)|指定されたファイル (静的関数) の名前を変更します。|  
|[CFile::Seek](#seek)|現在のファイル ポインターを移動します。|  
|[CFile::SeekToBegin](#seektobegin)|ファイルの先頭には、現在のファイル ポインターを移動します。|  
|[CFile::SeekToEnd](#seektoend)|ファイルの最後に、現在のファイル ポインターを配置します。|  
|[CFile::SetFilePath](#setfilepath)|選択したファイルの完全ファイル パスを設定します。|  
|[CFile::SetLength](#setlength)|ファイルの長さを変更します。|  
|[CFile::SetStatus](#setstatus)|指定されたファイル (静的、仮想関数) の状態を設定します。|  
|[CFile::UnlockRange](#unlockrange)|ファイル内のバイトの範囲のロックを解除します。|  
|[CFile::Write](#write)|現在の位置をファイルに (バッファーなし) のデータを書き込みます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFile::operator ハンドル](#operator_handle)|ハンドル、`CFile`オブジェクト。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFile::hFileNull](#hfilenull)|かどうかを`CFile`オブジェクトが有効なハンドル。|  
|[CFile::m_hFile](#m_hfile)|通常、オペレーティング システム ファイル ハンドルが含まれます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFile::m_pTM](#m_ptm)|ポインター`CAtlTransactionManager`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 バッファリングされていない、バイナリのディスク入力/出力のサービスを直接提供も直接サポートしていないテキスト ファイルとその派生クラスを使用してメモリ ファイル。 `CFile` 連携して、 `CArchive` Microsoft Foundation Class オブジェクトのシリアル化をサポートするクラス。  
  
 このクラスとその派生クラスの階層リレーションシップにより、プログラム、ポリモーフィックですべてのファイル オブジェクトを操作する`CFile`インターフェイスです。 メモリ ファイルは、たとえば、ディスク ファイルと同様に動作します。  
  
 使用して`CFile`と汎用的なディスク I/O の派生クラス。 使用して`ofstream`またはディスク ファイルに送信される書式設定されたテキストの他の Microsoft iostream クラスです。  
  
 通常、ディスク ファイルを開く時に自動的に`CFile`構築と破棄に終了します。 静的メンバー関数は、ファイルを開かずにファイルのステータスを調査することを許可します。  
  
 使用の詳細について`CFile`、記事を参照して[MFC のファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="abort"></a>  解放  
 このオブジェクトに関連付けられているファイルを閉じ、ファイルを読み取りや書き込みに対して使用できなくなります。  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを破棄する前に、ファイルを閉じていない場合、デストラクターがファイルを閉じます。  
  
 例外を処理するときに`CFile::Abort`異なる`CFile::Close`2 つの重要な点でします。 最初に、**中止**関数が例外をスローしませんエラー発生時によってエラーが無視されるため**中止**です。 2 番目、**中止**されません**ASSERT**ファイルが開かれていない、またはが以前に閉じられました。  
  
 使用した場合**新しい**を割り当て、`CFile`ヒープのオブジェクトの後に、ファイルを閉じて後に削除する必要があります。 **中止**設定`m_hFile`に`CFile::hFileNull`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]  
  
##  <a name="cfile"></a>  ほか  
 `CFile` オブジェクトを構築して初期化します。  
  
```  
CFile();  
CFile(CAtlTransactionManager* pTM);  
CFile(HANDLE hFile);

 
CFile(
LPCTSTR lpszFileName,  
UINT nOpenFlags);

 
CFile(
LPCTSTR lpszFileName,  
UINT nOpenFlags,  
CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>パラメーター  
 `hFile`  
 `CFile` オブジェクトにアタッチするためのファイル ハンドル。  
  
 `lpszFileName`  
 `CFile` オブジェクトにアタッチするための相対パスまたは完全パス。  
  
 `nOpenFlags`  
 指定されたファイルのファイル アクセス オプションのビットごとの組み合わせ (OR)。 使用できるオプションについては、「解説」を参照してください。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 次の 5 つの表は、`nOpenFlags` パラメーターの、使用できるオプションを示しています。  
  
 次のファイル アクセス モード オプションから 1 つのみ選択します。 既定のファイル アクセス モードは `CFile::modeRead` であり、これは読み取り専用です。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::modeRead`|読み取りアクセスのみを要求します。|  
|`CFile::modeWrite`|書き込みアクセスのみを要求します。|  
|`CFile::modeReadWrite`|読み取りおよび書き込みアクセスを要求します。|  
  
 次の文字モード オプションのいずれかを選択します。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::typeBinary`|バイナリ モードを設定します (派生クラスのみで使用されます)。|  
|`CFile::typeText`|(派生クラスのみで使用される) キャリッジ リターンとライン フィードのペアに対する特別な処理を伴うテキスト モードを設定します。|  
|`CFile::typeUnicode`|Unicode モードを設定します (派生クラスのみで使用されます)。 アプリケーションが Unicode 構成でビルドされた場合、テキストは Unicode 形式でファイルに書き込まれます。 BOM はファイルに書き込まれません。|  
  
 次のファイル共有モード オプションから 1 つのみ選択します。 既定のファイル共有モードは `CFile::shareExclusive` であり、これは排他的です。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::shareDenyNone`|共有の制限はありません。|  
|`CFile::shareDenyRead`|他のすべての読み取りアクセスを拒否します。|  
|`CFile::shareDenyWrite`|他のすべての書き込みアクセスを拒否します。|  
|`CFile::shareExclusive`|他のすべての読み取りおよび書き込みアクセスを拒否します。|  
  
 次のファイル作成モード オプションから最初のオプションまたは両方を選択します。 既定の作成モードは `CFile::modeNoTruncate` であり、これは既存を開くです。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::modeCreate`|ファイルが存在しない場合は、新しいファイルを作成します。 です。ファイルが既に存在する場合[CFileException](../../mfc/reference/cfileexception-class.md)が発生します。|  
|`CFile::modeNoTruncate`|ファイルが存在しない場合は新しいファイルを作成します。ファイルが既に存在する場合は、そのファイルが `CFile` オブジェクトにアタッチされます。|  
  
 説明に従って次のファイル キャッシュ オプションを選択します。 既定では、オプションとしては選択できない汎用のキャッシュ スキームが使用されます。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::osNoBuffer`|ファイルの中間キャッシュは使用されません。 このオプションを選択すると、次の 2 つのオプションは取り消されます。|  
|`CFile::osRandomAccess`|ファイル キャッシュはランダム アクセスに対して最適化されます。 このオプションと順次スキャン オプションを一緒に使用しないでください。|  
|`CFile::osSequentialScan`|ファイル キャッシュは順次アクセスに対して最適化されます。 このオプションとランダム アクセス オプションを一緒に使用しないでください。|  
|`CFile::osWriteThrough`|書き込み操作が遅延なしで実行されます。|  
  
 ファイル ハンドルが継承されないようにするために、次のセキュリティ オプションを選択します。 既定では、新しい子プロセスはファイル ハンドルを使用できます。  
  
|値|説明|  
|-----------|-----------------|  
|`CFile::modeNoInherit`|子プロセスがファイル ハンドルを使用できないようにします。|  
  
 既定のコンストラクターでは、メンバーは初期化されますが、ファイルは `CFile` オブジェクトにアタッチされません。 このコンス トラクターを使用すると、使用、 [CFile::Open](#open)ファイルを開くし、添付する方法、`CFile`オブジェクト。  
  
 1 つのパラメーターを持つコンストラクターでは、メンバーは初期化され、既存のファイルが `CFile` オブジェクトにアタッチされます。  
  
 2 つのパラメーターを持つコンストラクターでは、メンバーは初期化され、指定されたファイルを開くことが試行されます。 このコンストラクターによって、指定されたファイルが正常に開かれると、ファイルは `CFile` オブジェクトにアタッチされます。それ以外の場合は、このコンストラクターによって `CInvalidArgException` オブジェクトへのポインターがスローされます。 例外を処理する方法の詳細については、次を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)です。  
  
 `CFile` オブジェクトによって、指定されたファイルが正常に開かれた場合、このファイルは `CFile` オブジェクトが破棄されたときに自動的に閉じられます。それ以外の場合は、`CFile` オブジェクトにアタッチされなくなった後でファイルを明示的に閉じる必要があります。  
  
### <a name="example"></a>例  
 `CFile` の使用例を次のコードに示します。  
  
 [!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]  
  
##  <a name="close"></a>  データ  
 このオブジェクトに関連付けられているファイルを閉じ、ファイルを読み取りや書き込みに対して使用できなくなります。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを破棄する前に、ファイルを閉じていない場合、デストラクターがファイルを閉じます。  
  
 使用した場合**新しい**を割り当て、`CFile`ヒープのオブジェクトの後に、ファイルを閉じて後に削除する必要があります。 **閉じる**設定`m_hFile`に`CFile::hFileNull`です。  
  
### <a name="example"></a>例  
 例を参照して[ほか](#cfile)です。  
  
##  <a name="duplicate"></a>  CFile::Duplicate  
 重複を構築`CFile`指定されたファイルのオブジェクト。  
  
```  
virtual CFile* Duplicate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 重複するへのポインター`CFile`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 これは、C ランタイム関数に相当`_dup`です。  
  
##  <a name="flush"></a>  CFile::Flush  
 ファイルに書き込まれるファイル バッファーの残りの部分を強制します。  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>コメント  
 使用`Flush`のフラッシュも限りません`CArchive`バッファー。 アーカイブを使用している場合は、呼び出す[ときは](../../mfc/reference/carchive-class.md#flush)最初。  
  
### <a name="example"></a>例  
 例を参照して[CFile::SetFilePath](#setfilepath)です。  
  
##  <a name="getfilename"></a>  CFile::GetFileName  
 指定されたファイルの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルの名前です。  
  
### <a name="remarks"></a>コメント  
 たとえば、呼び出す`GetFileName`ファイルについてユーザーにメッセージを生成する`c:\windows\write\myfile.wri`、ファイル名、`myfile.wri`が返されます。  
  
 名前を含む、ファイルの完全パスを返す呼び出します[まで含めた](#getfilepath)です。 ファイルのタイトルを取得する ( `myfile`)、呼び出す[GetFileTitle](#getfiletitle)です。  
  
### <a name="example"></a>例  
 次のコード片では、システムが開きます。WINDOWS ディレクトリに INI ファイルです。 見つかると、例を印刷し、パスと名前、タイトル出力で示すようにします。  
  
 [!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]  
  
##  <a name="getfilepath"></a>  CFile::GetFilePath  
 指定されたファイルの完全なパスを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 指定されたファイルの完全パス。  
  
### <a name="remarks"></a>コメント  
 たとえば、呼び出す`GetFilePath`ファイルについてユーザーにメッセージを生成する`c:\windows\write\myfile.wri`、ファイル パスで`c:\windows\write\myfile.wri`が返されます。  
  
 ファイルの名前だけを返す ( `myfile.wri`)、呼び出す[GetFileName](#getfilename)です。 ファイルのタイトルを取得する ( `myfile`)、呼び出す[GetFileTitle](#getfiletitle)です。  
  
### <a name="example"></a>例  
 例を参照して[GetFileName](#getfilename)です。  
  
##  <a name="getfiletitle"></a>  CFile::GetFileTitle  
 ファイルのファイルのタイトル (表示名) を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 基になるファイルのタイトル。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924)ファイルのタイトルを取得します。 成功した場合、メソッドは、ユーザーにファイル名を表示したり、システムを使用する文字列を返します。 それ以外の場合、メソッドを呼び出して[PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589)を基になるファイルのファイル名 (ファイル拡張子を含む) を取得します。 そのため、返されるファイルのタイトルの文字列にファイルの拡張子が含まれません常にします。 詳細については、次を参照してください。 [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924)と[PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) Windows SDK に含まれています。  
  
 名前を含む、ファイルの完全パスを返す呼び出します[まで含めた](#getfilepath)です。 ファイルの名前だけを返すを呼び出す[GetFileName](#getfilename)です。  
  
### <a name="example"></a>例  
 例を参照して[GetFileName](#getfilename)です。  
  
##  <a name="getlength"></a>  結び付けてその中  
 現在の論理ファイルのバイトの長さを取得します。  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルの長さ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]  
  
##  <a name="getposition"></a>  実行  
 後続の呼び出しで使用できるファイル ポインターの現在の値を取得`Seek`です。  
  
```  
virtual ULONGLONG GetPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ファイルのポインターです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]  
  
##  <a name="getstatus"></a>  Cfile::getstatus  
 このメソッドに関連するステータス情報を取得する指定された`CFile`オブジェクト インスタンスまたは指定されたファイル パス。  
  
```  
BOOL GetStatus(CFileStatus& rStatus) const;  
  
static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,  
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `rStatus`  
 ユーザーが指定したへの参照を**CFileStatus**ステータス情報を受け取る。 **CFileStatus**構造体には、次のフィールド。  
  
- **CTime m_ctime**ファイルが作成された日付と時刻。  
  
- **CTime m_mtime**ファイルが最後に変更された日時。  
  
- **CTime m_atime**を読み取り、ファイルの最終アクセス日時。  
  
- **使い m_size** (バイト単位)、DIR コマンドによって報告されたファイルの論理サイズ。  
  
- **バイト m_attribute**ファイルの属性のバイト。  
  
- **char m_szFullName [_MAX_PATH]** Windows 文字セット内の絶対ファイル名。  
  
 `lpszFileName`  
 Windows の文字の文字列は、パスを設定、目的のファイル。 相対パスまたは絶対パスを指定できますか、ネットワーク パス名を含めることができます。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**指定されたファイルの状態情報が正常に取得した、それ以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 静的でないバージョンの**GetStatus**に関連付けられた開いているファイルのステータス情報を取得、指定された`CFile`オブジェクト。  静的バージョン**GetStatus**実際には、ファイルを開くことがなく、指定されたファイル パスからファイルの状態を取得します。 これは、ファイルの存在とアクセス権を調べるに役立ちます。  
  
 **M_attribute**のメンバー、 **CFileStatus**構造体は、ファイル属性のセットを参照します。 `CFile`クラスを提供、**属性**列挙型のため、シンボル ファイルの属性を指定することができます。  
  
```  
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```    
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]  
  
##  <a name="hfilenull"></a>  CFile::hFileNull  
 有効なファイル ハンドルの有無を判断、`CFile`オブジェクト。  
  
```  
static AFX_DATA const HANDLE hFileNull;  
```  
  
### <a name="remarks"></a>コメント  
 この定数はかどうかを使用、`CFile`オブジェクトが有効なファイル ハンドル。  
  
 次の例では、この操作を示しています。  
  
 [!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]  
  
##  <a name="lockrange"></a>  CFile::LockRange  
 例外をスローして、ファイルが既にロックされている場合、開いているファイル内のバイトの範囲をロックします。  
  
```  
virtual void LockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwPos`  
 ロックするバイト範囲の先頭のバイト オフセット。  
  
 `dwCount`  
 ロックする範囲のバイト数。  
  
### <a name="remarks"></a>コメント  
 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの 1 つ以上の領域をロックすることができますが、重なり合う領域は許可されていません。  
  
 使用して、領域のロックを解除するときに、`UnlockRange`メンバー関数は、バイト範囲は、以前にロックされている領域に正確に対応する必要があります。 `LockRange`関数は、隣接する領域をマージしません。 ロックされている 2 つの領域が隣接している場合は、する必要がありますロックを解除する各地域とは別にします。  
  
> [!NOTE]
>  この関数は、 `CMemFile`-クラスを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="m_hfile"></a>  CFile::m_hFile  
 開いているファイルのオペレーティング システム ファイル ハンドルが含まれています。  
  
```  
HANDLE m_hFile;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hFile` 型のパブリック変数**UINT**です。 含まれている`CFile::hFileNull`(空のファイルをオペレーティング システム独立インジケーター)、ハンドルが割り当てられていない場合。  
  
 使用`m_hFile`メンバーの意味は、派生クラスに依存するためには推奨されません。 `m_hFile` クラスを非ポリモーフィックなサポートするうえで利便性のためのパブリック メンバーになります。  
  
##  <a name="m_ptm"></a>  CFile::m_pTM  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="open"></a>  CFile::Open  
 オーバーロードされます。 **開いている**、既定で使用するために設計されていますが`CFile`コンス トラクターです。  
  
```  
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 目的のファイルのパスを表す文字列。 このパスは相対パス、絶対パス、またはネットワーク名 (UNC) にできます。  
  
 `nOpenFlags`  
 A **UINT**ファイルの共有とアクセス モードを定義します。 ファイルを開くときに実行するアクションを指定します。 ビットごとの OR を使用してオプションを組み合わせることができます ( **&#124;** ) 演算子。 1 つのアクセス許可と 1 つの共有のオプションが必要です。**modeCreate**と**modeNoInherit**モードは省略可能です。 参照してください、 [CFile](#cfile)モード オプションの一覧のコンス トラクターです。  
  
 `pError`  
 失敗した操作のステータスを受信する既存のファイルの例外オブジェクトへのポインター。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 開くが成功した場合は 0 以外。それ以外の場合 0 を返します。 `pError`パラメーターは 0 が返される場合にのみ意味を持ちます。  
  
### <a name="remarks"></a>コメント  
 2 つの関数は、通常は失敗ファイルを開くための「安全な」メソッドを形成します。  
  
 中に、`CFile`コンス トラクターは、エラー状態で例外をスロー**開く**が返されます**FALSE**エラー条件。 **開いている**初期化できますが、 [CFileException](../../mfc/reference/cfileexception-class.md)ただし、エラーを記述するオブジェクト。 指定しない場合、`pError`パラメーター、またはを渡した場合**NULL**の`pError`、**開く**が返されます**FALSE**スローしないと、`CFileException`です。 既存のポインターを渡す場合`CFileException`、および**開く**エラー検出すると、関数がいっぱいに、そのエラーを説明する情報を使用します。 どちらのケースは**開く**例外をスローします。  
  
 次の表に、考えられる結果の**開く**です。  
  
|`pError`|エラーが発生しました|戻り値|CFileException コンテンツ|  
|--------------|------------------------|------------------|----------------------------|  
|**NULL**|いいえ|**場合は TRUE。**|N/A|  
|ポインター `CFileException`|いいえ|**場合は TRUE。**|変更なし|  
|**NULL**|[はい]|**FALSE**|N/A|  
|ポインター `CFileException`|[はい]|**FALSE**|エラーを記述する初期化|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]  
  
##  <a name="operator_handle"></a>  CFile::operator ハンドル  
 この演算子を識別するハンドルを使用して、`CFile`などの関数オブジェクト[ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468)と[GetFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724320)を想定して、`HANDLE`です。  
  
```  
operator HANDLE() const;  
```  
  
##  <a name="read"></a>  :Read  
 関連付けられているファイルからバッファーにデータを読み取り、`CFile`オブジェクト。  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 ファイルから読み取られるデータを受信するユーザーが指定したバッファーへのポインター。  
  
 `nCount`  
 ファイルから読み取られるバイトの最大数。 テキスト モードのファイルには、キャリッジ リターンとライン フィードのペアは 1 つの文字としてカウントされます。  
  
### <a name="return-value"></a>戻り値  
 バッファーに転送するバイト数。 すべての`CFile`クラスを戻り値にすることがありますより小さい`nCount`ファイルの末尾に達した場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]  
  
 別の例を参照してください。 [CFile::Open](#open)です。  
  
##  <a name="remove"></a>  CFile::Remove  
 この静的関数では、パスで指定されたファイルを削除します。  
  
```  
static void PASCAL Remove(
    LPCTSTR lpszFileName, 
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 目的のファイルのパスを表す文字列。 パスは相対パスまたは絶対とネットワーク名を含めることができます。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 ディレクトリは削除されません。  
  
 **削除**接続されているファイルが開いている場合、またはファイルを削除できない場合は、メンバー関数が例外をスローします。 これは、DEL コマンドに相当します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]  
  
##  <a name="rename"></a>  CFile::Rename  
 この静的関数には、指定したファイルが名前を変更します。  
  
```  
static void PASCAL Rename(
    LPCTSTR lpszOldName,  
    LPCTSTR lpszNewName,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszOldName`  
 古いパスです。  
  
 `lpszNewName`  
 新しいパス。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 ディレクトリの名前を変更することはできません。 これは、REN コマンドに相当します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]  
  
##  <a name="seek"></a>  CFile::Seek  
 開いているファイルのファイル ポインターを移動します。  
  
```  
virtual ULONGLONG Seek(
LONGLONG lOff,  
UINT nFrom);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOff`  
 ファイル ポインターを移動するバイト数。 正の値が、ファイルの末尾にかけてファイル ポインターを移動します。負の値は、ファイルの先頭に向かってファイル ポインターを移動します。  
  
 `nFrom`  
 シークを開始する位置。 使用可能な値は、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、ファイル ポインターの位置それ以外の場合、戻り値は未定義とへのポインター、`CFileException`例外がスローされます。  
  
### <a name="remarks"></a>コメント  
 次の表に、可能な値、`nFrom`パラメーター。  
  
|[値]|説明|  
|-----------|-----------------|  
|`CFile::begin`|ファイルの先頭からのシークします。|  
|`CFile::current`|シーク ファイル ポインターの現在の場所からします。|  
|`CFile::end`|ファイルの末尾からのシークします。|  
  
 ファイルが開かれたときに、ファイル ポインターは、0 の場合、ファイルの先頭に配置されます。  
  
 ファイル ポインターは、ファイルの末尾の次の位置を設定できます。 これを行う場合、ファイルのサイズは、ファイルに書き込むまで増加しません。  
  
 このメソッドの例外ハンドラーは、例外が処理された後、例外オブジェクトを削除する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]  
  
##  <a name="seektobegin"></a>  CFile::SeekToBegin  
 ファイルの先頭には、ファイル ポインターの値を設定します。  
  
```  
void SeekToBegin();
```  
  
### <a name="remarks"></a>コメント  
 `SeekToBegin()` は `Seek( 0L, CFile::begin )` と同じです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="seektoend"></a>  CFile::SeekToEnd  
 論理ファイルの末尾にファイル ポインターの値を設定します。  
  
```  
ULONGLONG SeekToEnd();
```  
  
### <a name="return-value"></a>戻り値  
 ファイルの長さをバイト単位で返します。  
  
### <a name="remarks"></a>コメント  
 `SeekToEnd()` は `CFile::Seek( 0L, CFile::end )` と同じです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="setfilepath"></a>  CFile::SetFilePath  
 ファイルのパスを指定するには、この関数を呼び出すたとえば、次の場合、ファイルのパスは使用できません、 [CFile](../../mfc/reference/cfile-class.md)オブジェクトを構築、呼び出す`SetFilePath`を指定します。  
  
```  
virtual void SetFilePath(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszNewName`  
 新しいパスを指定する文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
> `SetFilePath` いないファイルを開くか、ファイルを作成しませんこれを単に関連付ける、`CFile`オブジェクトを使用してパス名を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]  
  
##  <a name="setlength"></a>  CFile::SetLength  
 ファイルの長さを変更するには、この関数を呼び出します。  
  
```  
virtual void SetLength(ULONGLONG dwNewLen);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwNewLen`  
 目的のファイルのバイトの長さです。 この値は、ファイルの現在の長さより大きくまたは小さくすることができます。 このファイルは拡張か、必要に応じて切り捨てられます。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  `CMemFile`、この関数は、`CMemoryException`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]  
  
##  <a name="setstatus"></a>  CFile::SetStatus  
 このファイルの場所に関連付けられているファイルの状態を設定します。  
  
```  
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,  
    const CFileStatus& status,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 目的のファイルのパスを表す文字列。 パスは相対パスまたは絶対とネットワーク名を含めることができます。  
  
 *status*  
 新しいステータス情報を保持するバッファー。 呼び出す、 **GetStatus** prefill するメンバー関数、 **CFileStatus**を現在の値を構造化し、必要に応じて変更します。 値が 0 の場合、対応する状態の項目は更新されません。 参照してください、 [GetStatus](#getstatus)メンバー関数の詳細については、 **CFileStatus**構造体。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 時間を設定するには、変更、 **m_mtime**フィールド*ステータス*です。  
  
 呼び出しを行うとことに注意してください`SetStatus`、ファイルの属性のみを変更しようと**m_mtime**ファイルの状態の構造体のメンバーがゼロ以外、属性も影響を受ける可能性 (タイムスタンプを変更します。副作用にあります属性)。 ファイルの属性だけを変更する場合は、まず設定、 **m_mtime** 、ファイルの状態構造体のメンバーがゼロにへの呼び出しを行う`SetStatus`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]  
  
##  <a name="unlockrange"></a>  CFile::UnlockRange  
 開いているファイル内のバイト範囲ロックを解除します。  
  
```  
virtual void UnlockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwPos`  
 ロックを解除するバイトの範囲の先頭のバイト オフセット。  
  
 `dwCount`  
 ロックを解除する範囲のバイト数。  
  
### <a name="remarks"></a>コメント  
 説明を参照して、 [LockRange](#lockrange)詳細については、メンバー関数。  
  
> [!NOTE]
>  この関数は、 `CMemFile`-クラスを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="write"></a>  CFile::Write  
 バッファーからデータに関連付けられているファイルに書き込みます、`CFile`オブジェクト。  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuf`  
 ファイルに書き込まれるデータを格納しているユーザーが指定したバッファーへのポインター。  
  
 `nCount`  
 バッファーから転送されるバイト数。 テキスト モードのファイルには、キャリッジ リターンとライン フィードのペアは 1 つの文字としてカウントされます。  
  
### <a name="remarks"></a>コメント  
 **書き込む**ディスクの空き容量の条件を含む、いくつかの条件への応答で例外をスローします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]  
  
 さらに、例を参照[ほか](#cfile)と[CFile::Open](#open)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DRAWCLI](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStdioFile クラス](../../mfc/reference/cstdiofile-class.md)   
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)
