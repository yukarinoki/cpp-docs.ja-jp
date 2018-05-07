---
title: CStdioFile クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
dev_langs:
- C++
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89de8dddae6d6549fe12086b84e6bb656afcbc4f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cstdiofile-class"></a>CStdioFile クラス
ランタイム関数によって開かれると、C ランタイム ストリーム ファイルを表す[fopen](../../c-runtime-library/reference/fopen-wfopen.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
class CStdioFile : public CFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStdioFile::CStdioFile](#cstdiofile)|構築、`CStdioFile`パスまたはファイルへのポインターからのオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStdioFile::Open](#open)|オーバーロードされます。 開くが、既定で使用するために設計された`CStdioFile`コンス トラクター (オーバーライド[CFile::Open](../../mfc/reference/cfile-class.md#open))。|  
|[CStdioFile::ReadString](#readstring)|1 行のテキストを読み取ります。|  
|[CStdioFile::Seek](#seek)|現在のファイル ポインターを移動します。|  
|[CStdioFile::WriteString](#writestring)|1 行のテキストを書き込みます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CStdioFile::m_pStream](#m_pstream)|開いているファイルへのポインターが含まれています。|  
  
## <a name="remarks"></a>コメント  
 ストリームのファイルは、バッファーに格納され、テキスト モード (既定) またはバイナリ モードのいずれかで開くことができます。  
  
 テキスト モードでは、キャリッジ リターンとライン フィードのペアに対する特別な処理を提供します。 改行文字を記述するとき文字 (0x0A) テキスト モードを`CStdioFile`オブジェクト、バイトのペア (0x0D、0x0A) は、ファイルに送信します。 読み込みのときは、バイトのペア (0x0D、0x0A) 0x0A の 1 バイトに変換されます。  
  
 [CFile](../../mfc/reference/cfile-class.md)関数[複製](../../mfc/reference/cfile-class.md#duplicate)、 [LockRange](../../mfc/reference/cfile-class.md#lockrange)、および[UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)はサポートされていません`CStdioFile`です。  
  
 これらの関数を呼び出す場合、 `CStdioFile`、表示される、[行わない](../../mfc/reference/cnotsupportedexception-class.md)です。  
  
 使用の詳細について`CStdioFile`、記事を参照して[MFC のファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cstdiofile"></a>  CStdioFile::CStdioFile  
 `CStdioFile` オブジェクトを構築して初期化します。  
  
```  
CStdioFile();  
CStdioFile(CAtlTransactionManager* pTM);  
  CStdioFile(FILE* pOpenStream);

 
CStdioFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags);

 
CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>パラメーター  
 `pOpenStream`  
 C ランタイム関数への呼び出しによって返されるファイル ポインターを指定[fopen](../../c-runtime-library/reference/fopen-wfopen.md)です。  
  
 `lpszFileName`  
 目的のファイルへのパスを表す文字列を指定します。 相対パスまたは絶対パスができます。  
  
 `nOpenFlags`  
 ファイルの作成、ファイル共有、およびファイル アクセス モードのオプションを指定します。 ビットごとの OR を使用して複数のオプションを指定することができます ( `|`) 演算子。  
  
 1 つのファイル アクセス モード オプションが必要です。その他のモードはオプションです。 参照してください[ほか](../../mfc/reference/cfile-class.md#cfile)モード オプションおよびその他のフラグの一覧についてはします。 Mfc バージョン 3.0 以降では、共有フラグが許可されます。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定のコンス トラクターがファイルを添付できません、`CStdioFile`オブジェクト。 使用する必要がありますをこのコンス トラクターを使用する場合、`CStdioFile::Open`ファイルを開くし、添付する方法、`CStdioFile`オブジェクト。  
  
 単一パラメーター コンス トラクターは、アタッチするためのファイルを開くストリーム、`CStdioFile`オブジェクト。 定義済みの入力/出力ファイル ポインターのポインター値が許可されている`stdin`、 `stdout`、または`stderr`です。  
  
 2 つのパラメーターのコンス トラクターを作成、`CStdioFile`オブジェクトを指定されたパスに対応するファイルを開きます。  
  
 渡す場合`NULL`いずれかの`pOpenStream`または`lpszFileName`、コンス トラクターは、スロー、`CInvalidArgException*`です。  
  
 ファイルを開いたり作成したりすることはできません、コンス トラクターは、スロー、`CFileException*`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]  
  
##  <a name="m_pstream"></a>  CStdioFile::m_pStream  
 `m_pStream`データ メンバーは、C ランタイム関数によって返されるように、開いているファイルへのポインターは`fopen`します。  
  
```  
FILE* m_pStream;  
```  
  
### <a name="remarks"></a>コメント  
 **NULL**ファイルが開かれていなかったまたはが閉じられました。  
  
##  <a name="open"></a>  CStdioFile::Open  
 オーバーロードされます。 開くが、既定で使用するために設計された`CStdioFile`コンス トラクターです。  
  
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
 目的のファイルのパスを表す文字列。 相対パスまたは絶対パスができます。  
  
 `nOpenFlags`  
 共有とアクセス モードです。 ファイルを開くときに実行するアクションを指定します。 ビットごとの OR を使用してオプションを組み合わせることができます (&#124;) 演算子。 1 つのアクセス許可と 1 つの共有のオプションが必要です。modeCreate と modeNoInherit モードはオプションです。  
  
 `pError`  
 失敗した操作のステータスを受信する既存のファイルの例外オブジェクトへのポインター。  
  
 `pTM`  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="readstring"></a>  CStdioFile::ReadString  
 上限に達するまで、バッファーにテキスト データを読み取ります`nMax`に関連付けられているファイルから、-1 が文字、`CStdioFile`オブジェクト。  
  
```  
virtual LPTSTR ReadString(
    LPTSTR lpsz,  
    UINT nMax);  
  
virtual BOOL ReadString(CString& rString);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 Null で終わる文字列を受信するユーザーが指定したバッファーへのポインターを指定します。  
  
 `nMax`  
 終端の null 文字をカウントせず、読み取る文字の最大数を指定します。  
  
 `rString`  
 参照、`CString`関数が戻るときに、文字列を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 テキスト データを格納するバッファーへのポインター。 **NULL**場合はブール値、またはすべてのデータを読み取り中にファイルの終端に達した場合**FALSE**データを読み込まずにファイルの終端に達した場合。  
  
### <a name="remarks"></a>コメント  
 最初の改行文字では、読み取りが停止します。 その場合より少ない場合、 `nMax`-1 文字が読み取られた、改行文字は、バッファーに格納します。 どちらの場合は、null 文字 ('\0') が追加されます。  
  
 [:Read](../../mfc/reference/cfile-class.md#read)はキャリッジ リターンとライン フィードのペアに対してがテキスト モードの入力を終了しないにも使用できます。  
  
> [!NOTE]
>  `CString`この関数のバージョンを削除、`'\n'`存在する場合、`LPTSTR`バージョンではありません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]  
  
##  <a name="seek"></a>  CStdioFile::Seek  
 以前に開かれたファイルのポインターを移動します。  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOff,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>パラメーター  
 `lOff`  
 ポインターを移動するバイト数。  
  
 `nFrom`  
 ポインターの移動モード。 次の値のいずれかを指定する必要があります。  
  
- `CFile::begin`: ファイル ポインターを移動`lOff`ファイルの先頭からのバイト数を転送します。  
  
- `CFile::current`: ファイル ポインターを移動`lOff`ファイル内の現在位置からのバイト数。  
  
- `CFile::end`: ファイル ポインターを移動`lOff`ファイルの末尾からのバイト数。 なお`lOff`必要がある既存にシークする負ファイルです。 正の値は、ファイルの末尾を越えたシークします。  
  
### <a name="return-value"></a>戻り値  
 場合は、要求された位置は法律、`Seek`ファイルの先頭から新しいバイト オフセットを返します。 それ以外の場合、戻り値は未定義と`CFileException`オブジェクトがスローされます。  
  
### <a name="remarks"></a>コメント  
 `Seek`関数により、ファイルの内容へのランダム アクセス、ポインターを移動することによって、指定した量絶対的または相対的です。 データは、検索中に実際には読み込まれません。 要求された位置が、ファイルのサイズより大きい場合は、ファイルの長さは、その位置まで拡張して、例外はスローされません。  
  
 ファイルが開かれたときに、ファイル ポインターがオフセット 0 の場合、ファイルの先頭に配置されます。  
  
 この実装`Seek`ランタイム ライブラリ (CRT) 関数に基づく`fseek`です。 使用法にいくつかの制限は`Seek`テキスト モードで開いたストリームでします。 詳細については、次を参照してください。 [fseek、_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)です。  
  
### <a name="example"></a>例  
 次の例は、使用する方法を示しています。`Seek`の先頭から 1000 バイトのポインターを移動する、`cfile`ファイル。 なお`Seek`読み取れないデータを後で呼び出す必要がありますので[CStdioFile::ReadString](#readstring)データを読み取れません。  
  
 [!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]  
  
##  <a name="writestring"></a>  CStdioFile::WriteString  
 バッファーからデータに関連付けられているファイルに書き込みます、`CStdioFile`オブジェクト。  
  
```  
virtual void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 Null で終わる文字列を格納するバッファーへのポインターを指定します。  
  
### <a name="remarks"></a>コメント  
 終端の null 文字 ( `\0`) は、ファイルに書き込まれません。 このメソッドでは、改行文字を書き込みます`lpsz`キャリッジ リターン/ライン フィードのペアとしてファイルにします。  
  
 Null で終わるファイルを使用するデータを書き込む場合`CStdioFile::Write`または[CFile::Write](../../mfc/reference/cfile-class.md#write)です。  
  
 このメソッドは、`CInvalidArgException*`を指定する場合`NULL`の`lpsz`パラメーター。  
  
 このメソッドは、`CFileException*`ファイル システム エラーに応答します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)   
 [CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)   
 [CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)   
 [CNotSupportedException クラス](../../mfc/reference/cnotsupportedexception-class.md)
