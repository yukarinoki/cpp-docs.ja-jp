---
title: CArchive クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArchive
- AFX/CArchive
- AFX/CArchive::CArchive
- AFX/CArchive::Abort
- AFX/CArchive::Close
- AFX/CArchive::Flush
- AFX/CArchive::GetFile
- AFX/CArchive::GetObjectSchema
- AFX/CArchive::IsBufferEmpty
- AFX/CArchive::IsLoading
- AFX/CArchive::IsStoring
- AFX/CArchive::MapObject
- AFX/CArchive::Read
- AFX/CArchive::ReadClass
- AFX/CArchive::ReadObject
- AFX/CArchive::ReadString
- AFX/CArchive::SerializeClass
- AFX/CArchive::SetLoadParams
- AFX/CArchive::SetObjectSchema
- AFX/CArchive::SetStoreParams
- AFX/CArchive::Write
- AFX/CArchive::WriteClass
- AFX/CArchive::WriteObject
- AFX/CArchive::WriteString
- AFX/CArchive::m_pDocument
dev_langs:
- C++
helpviewer_keywords:
- CArchive [MFC], CArchive
- CArchive [MFC], Abort
- CArchive [MFC], Close
- CArchive [MFC], Flush
- CArchive [MFC], GetFile
- CArchive [MFC], GetObjectSchema
- CArchive [MFC], IsBufferEmpty
- CArchive [MFC], IsLoading
- CArchive [MFC], IsStoring
- CArchive [MFC], MapObject
- CArchive [MFC], Read
- CArchive [MFC], ReadClass
- CArchive [MFC], ReadObject
- CArchive [MFC], ReadString
- CArchive [MFC], SerializeClass
- CArchive [MFC], SetLoadParams
- CArchive [MFC], SetObjectSchema
- CArchive [MFC], SetStoreParams
- CArchive [MFC], Write
- CArchive [MFC], WriteClass
- CArchive [MFC], WriteObject
- CArchive [MFC], WriteString
- CArchive [MFC], m_pDocument
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0bfca3c6e42c8b4efa6cd29d86a30f36fc394f5
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952506"
---
# <a name="carchive-class"></a>CArchive クラス
使用すると、それらのオブジェクトを削除した後が引き続き発生する永続的なバイナリ形式 (通常はディスク ストレージ) にオブジェクトの複雑なネットワークを保存できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CArchive  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CArchive::CArchive](#carchive)|`CArchive` オブジェクトを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CArchive::Abort](#abort)|例外をスローせず、アーカイブを閉じます。|  
|[CArchive::Close](#close)|書き込まれていないデータをフラッシュし、切断、`CFile`です。|  
|[ときは](#flush)|アーカイブ バッファーから書き込まれていないデータをフラッシュします。|  
|[CArchive::GetFile](#getfile)|取得、`CFile`このアーカイブのオブジェクトのポインター。|  
|[CArchive::GetObjectSchema](#getobjectschema)|呼び出される、`Serialize`逆シリアル化されるオブジェクトのバージョンを判断する関数。|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Windows ソケットの中にバッファーが空になっているかどうかを決定プロセスを受信します。|  
|[場合](#isloading)|アーカイブを読み込むかどうかを判断します。|  
|[用](#isstoring)|アーカイブを格納するかどうかを判断します。|  
|[CArchive::MapObject](#mapobject)|マップ ファイルにシリアル化されませんを参照するサブオブジェクトの利用可能なオブジェクトを配置します。|  
|[読み書きするとき](#read)|生のバイトを読み取ります。|  
|[場合](#readclass)|クラスの参照が格納されていた読み取り`WriteClass`です。|  
|[CArchive::ReadObject](#readobject)|オブジェクトの呼び出し`Serialize`読み込みのための関数。|  
|[CArchive::ReadString](#readstring)|1 行のテキストを読み取ります。|  
|[CArchive::SerializeClass](#serializeclass)|読み取りまたは書き込みをクラスの参照を`CArchive`の方向に依存するオブジェクト、`CArchive`です。|  
|[CArchive::SetLoadParams](#setloadparams)|ロード配列を拡張するサイズを設定します。 任意のオブジェクトが読み込まれる前に、または前に呼び出す必要があります`MapObject`または`ReadObject`と呼びます。|  
|[CArchive::SetObjectSchema](#setobjectschema)|アーカイブ オブジェクトに格納されているオブジェクトのスキーマを設定します。|  
|[CArchive::SetStoreParams](#setstoreparams)|ハッシュ テーブルのサイズと、シリアル化プロセス中に一意のオブジェクトを識別するために使用するマップのブロック サイズを設定します。|  
|[CArchive::Write](#write)|生のバイトを書き込みます。|  
|[CArchive::WriteClass](#writeclass)|参照を書き込みます、`CRuntimeClass`を`CArchive`です。|  
|[CArchive::WriteObject](#writeobject)|オブジェクトの呼び出し`Serialize`を格納するための関数。|  
|[CArchive::WriteString](#writestring)|1 行のテキストを書き込みます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CArchive::operator &lt;&lt;](#operator_lt_lt)|オブジェクトとアーカイブをするプリミティブ型を格納します。|  
|[CArchive::operator &gt;&gt;](#operator_gt_gt)|アーカイブからオブジェクトとのプリミティブ型を読み込みます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CArchive::m_pDocument](#m_pdocument)||  
  
## <a name="remarks"></a>Remarks  
 `CArchive` 基本クラスはありません。  
  
 後でメモリに保持して再構築、永続的な記憶領域からオブジェクトを読み込むことができます。 データを永続的に行うには、このプロセスは「シリアル化します」と呼ばれる  
  
 アーカイブ オブジェクトをバイナリ ストリームの種類として考えることができます。 入力/出力ストリームのようにアーカイブがファイルに関連付けられ、バッファー内の書き込みおよび記憶域とデータの読み取りを許可します。 入力/出力ストリームは、ASCII 文字のシーケンスを処理しますが、アーカイブが非冗長、効率的な形式でバイナリ オブジェクト データを処理します。  
  
 作成する必要があります、 [CFile](../../mfc/reference/cfile-class.md)オブジェクトを作成する前に、`CArchive`オブジェクト。 さらに、アーカイブの読み込み/ストアの状態がファイルのオープン モードと互換性があることを確認する必要があります。 1 つのアクティブなアーカイブ ファイルごとに制限されます。  
  
 構築する場合、`CArchive`オブジェクト、クラスのオブジェクトにアタッチする`CFile`(または派生クラス) を表す、開いているファイル。 また、アーカイブを読み込み、または格納用に使用するかどうかも指定します。 A`CArchive`プリミティブ型だけでなく、オブジェクトのオブジェクトを処理できる[CObject](../../mfc/reference/cobject-class.md)-派生クラスがシリアル化のために設計されています。 シリアル化可能なクラスには通常、`Serialize`メンバー関数は、通常パラメーターを使用して、 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロ、クラスの下の説明に従って`CObject`です。  
  
 オーバー ロードされた抽出 ( **>>**) と挿入 ( **<<**) 演算子は、両方のプリミティブ型をサポートする便利なアーカイブ プログラミング インターフェイスと`CObject`派生クラス。  
  
 `CArchive` MFC Windows ソケット クラスを使用したプログラミングをサポートも[CSocket](../../mfc/reference/csocket-class.md)と[CSocketFile](../../mfc/reference/csocketfile-class.md)です。 [時](#isbufferempty)メンバー関数は、その使用をサポートしています。  
  
 詳細については`CArchive`、記事を参照して[シリアル化](../../mfc/serialization-in-mfc.md)と[Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CArchive`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afx.h  
  
##  <a name="abort"></a>  CArchive::Abort  
 この関数では、例外をスローせず、アーカイブを閉じます。  
  
```  
void Abort ();
```  
  
### <a name="remarks"></a>Remarks  
 `CArchive`デストラクターを呼び出す通常`Close`、保存されていないすべてのデータをフラッシュするが、関連付けられている`CFile`オブジェクト。 これにより、例外が発生します。  
  
 これらの例外をキャッチする場合を使用することをお勧め`Abort`、破棄されるように、`CArchive`オブジェクトな例外が発生します。 例外を処理するときに`CArchive::Abort`ために、エラーに例外をスローしませんとは異なり[CArchive::Close](#close)、`Abort`障害を無視します。  
  
 使用した場合**新しい**を割り当て、`CArchive`ヒープのオブジェクトの後に、ファイルを閉じて後に削除する必要があります。  
  
### <a name="example"></a>例  
  例を参照して[CArchive::WriteClass](#writeclass)です。  
  
##  <a name="carchive"></a>  CArchive::CArchive  
 構築、`CArchive`オブジェクトを読み込み、またはオブジェクトの格納に使用するかどうかを指定します。  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFile*  
 ポインター、`CFile`最終的な送信元または永続的なデータの送信先であるオブジェクト。  
  
 *nMode*  
 オブジェクトがから読み込まれたか、アーカイブに格納されているかどうかを指定するフラグ。 *NMode*パラメーターには、次の値のいずれかが必要があります。  
  
- **CArchive::load**アーカイブからデータを読み込みます。 だけで済みます`CFile`読み取りアクセス許可。  
  
- **CArchive::store**データをアーカイブに保存します。 必要があります`CFile`書き込みアクセス許可。  
  
- **CArchive::bNoFlushOnDelete**から自動的に呼び出すことにより、アーカイブ`Flush`アーカイブ デストラクターが呼び出されます。 このフラグを設定する場合、必要があります明示的に呼び出す`Close`デストラクターが呼び出される前にします。 そうしないと、データが破損します。  
  
 *nBufSize*  
 内部ファイル バッファーのサイズをバイト単位で指定する整数。 既定のバッファー サイズは 4,096 バイトであることに注意してください。 ラージ オブジェクトを定期的にアーカイブする場合は、ファイル バッファーのサイズの倍数では大きなバッファー サイズを使用する場合、パフォーマンスが向上します。  
  
 *lpBuf*  
 ユーザーが指定したサイズのバッファーへの省略可能なポインター *nBufSize*です。 このパラメーターを指定しない場合、アーカイブはバッファーがローカル ヒープから割り当てられ、オブジェクトが破棄されるときに、それを解放します。 アーカイブは、ユーザーが指定したバッファーを解放しません。  
  
### <a name="remarks"></a>Remarks  
 アーカイブを作成した後、この仕様を変更することはできません。  
  
 使用することは`CFile`アーカイブを終了するまで、ファイルの状態を変更する操作。 このような操作には、アーカイブの整合性が破損します。 アーカイブのファイル オブジェクトを取得することによってシリアル化中にいつでもファイル ポインターの位置にアクセスする可能性があります、 [GetFile](#getfile)メンバー関数を使用して、[実行](../../mfc/reference/cfile-class.md#getposition)関数. 呼び出す必要があります[ときは](#flush)ファイル ポインターの位置を取得する前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="close"></a>  CArchive::Close  
 バッファーに残っているデータをフラッシュ アーカイブを閉じ、アーカイブ ファイルから接続を切断します。  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Remarks  
 アーカイブで他の操作が許可されていません。 アーカイブを閉じた後、同じファイルに対して別のアーカイブを作成するまたはファイルを閉じることができます。  
  
 このメンバー関数は`Close`により、ファイルをアーカイブからすべてのデータを転送し、アーカイブを使用できなくなります。 ストレージ メディアには、ファイルからの転送を完了する必要があります最初に使用する[先](../../mfc/reference/cfile-class.md#close)し、破棄、`CFile`オブジェクト。  
  
### <a name="example"></a>例  
  例を参照して[CArchive::WriteString](#writestring)です。  
  
##  <a name="flush"></a>  ときは  
 ファイルに書き込まれるアーカイブ バッファーに残っているデータを強制します。  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は`Flush`ファイルにアーカイブからすべてのデータが転送されることを確認します。 呼び出す必要があります[先](../../mfc/reference/cfile-class.md#close)ストレージ メディアには、ファイルからの転送を完了します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="getfile"></a>  CArchive::GetFile  
 取得、`CFile`このアーカイブのオブジェクトのポインター。  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 定数ポインター、`CFile`使用中のオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 使用する前にアーカイブをフラッシュする必要があります`GetFile`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="getobjectschema"></a>  CArchive::GetObjectSchema  
 この関数から呼び出す、`Serialize`現在逆シリアル化されるオブジェクトのバージョンを判断する関数。  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>戻り値  
 シリアル化解除は、読み取られているオブジェクトのバージョン。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出す場合のみを有効、`CArchive`オブジェクトが読み込まれている ([場合](#isloading)0 以外を返します)。 最初の呼び出しをする必要があります、`Serialize`関数と呼び出し先は 1 回のみです。 戻り値 ( **UINT**)-1 では、バージョン番号が不明であることを示します。  
  
 A `CObject`-派生クラスが使用することがあります**VERSIONABLE_SCHEMA**結合 (ビット演算子を使用して**または**)、スキーマ バージョンと自体 (IMPLEMENT_SERIAL マクロ) では、「バージョン管理可能オブジェクト」を作成する、オブジェクトの`Serialize`メンバー関数は、複数のバージョンを読み取ることができます。 既定のフレームワークの機能 (せず**VERSIONABLE_SCHEMA**) は、バージョンが一致しない場合、例外をスローします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="isbufferempty"></a>  CArchive::IsBufferEmpty  
 アーカイブ オブジェクトの内部バッファーが空かどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アーカイブのバッファーが空である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数に MFC Windows ソケット クラスを使用したプログラミングをサポートするために指定された`CSocketFile`です。 関連付けられているアーカイブを使用する必要はありません、`CFile`オブジェクト。  
  
 使用する理由`IsBufferEmpty`に関連付けられているアーカイブを使用して、`CSocketFile`オブジェクトは、アーカイブのバッファーが 1 つ以上のメッセージまたはレコードを含む可能性があります。 1 つのメッセージを受信した後必要がありますを使用する`IsBufferEmpty`バッファーが空になるまでデータの受信を継続するループを制御します。 詳細については、次を参照してください。、[受信](../../mfc/reference/casyncsocket-class.md#receive)クラスのメンバー関数`CAsyncSocket`、使用する方法を示す`IsBufferEmpty`です。  
  
 詳細については、次を参照してください。 [Windows ソケット: アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
##  <a name="isloading"></a>  場合  
 アーカイブのデータの読み込みがあるかどうかを判断します。  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アーカイブが現在読み込み; のために使用されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 によって呼び出されます、`Serialize`アーカイブ済みのクラスの関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="isstoring"></a>  用  
 アーカイブがデータを格納するかどうかを判断します。  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アーカイブが現在; を格納するために使用されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 によって呼び出されます、`Serialize`アーカイブ済みのクラスの関数。  
  
 場合、`IsStoring`アーカイブの状態は 0 以外の場合、その`IsLoading`ステータスは 0、またはその逆です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="mapobject"></a>  CArchive::MapObject  
 参照のサブオブジェクトとして提供される、ファイルを実際にシリアル化されませんをマップにオブジェクトを配置するには、このメンバー関数を呼び出します。  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>パラメーター  
 *私書箱*  
 格納されているオブジェクトへの定数ポインター。  
  
### <a name="remarks"></a>Remarks  
 たとえば、ドキュメントをシリアル化する可能性がありますいないが、ドキュメントの一部である項目をシリアル化します。 呼び出して`MapObject`、それらのアイテム、またはドキュメントを参照する、サブオブジェクトを許可します。 また、シリアル化されたサブ項目をシリアル化できる、 *m_pDocument*バック ポインター。  
  
 呼び出すことができます`MapObject`に格納しからの読み込み、`CArchive`オブジェクト。 `MapObject` 管理されている内部データ構造を指定したオブジェクトを追加、`CArchive`オブジェクトとは異なりが、シリアル化および逆シリアル化中に[ReadObject](#readobject)と[WriteObject](#writeobject) **、** 呼び出しませんオブジェクトのシリアル化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="m_pdocument"></a>  CArchive::m_pDocument  
 設定**NULL**既定では、このポインターを`CDocument`のユーザーに何かに設定できる、`CArchive`要望をインスタンス化します。  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>Remarks  
 This ポインターの一般的な使用方法では、シリアル化されるすべてのオブジェクトをシリアル化プロセスに関する追加情報を伝えるためです。 これは、ドキュメントでマウス ポインターを初期化することによって実現 (、 `CDocument`-派生クラス) がシリアル化される、このような形で必要な場合、ドキュメント内のオブジェクトにドキュメントをアクセスできます。 このポインターはによっても使用`COleClientItem`シリアル化中にオブジェクト。  
  
 Framework セット*m_pDocument*ユーザーがファイルを発行するときにシリアル化されるドキュメントを開くか、コマンドを保存します。 明示的に設定する必要がある場合は、Object Linking and Embedding (OLE) コンテナーのドキュメント ファイルを開くまたは保存以外の理由をシリアル化する*m_pDocument*です。 たとえば、これを実行する、クリップボードにコンテナーのドキュメントをシリアル化するとき。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]  
  
##  <a name="operator_lt_lt"></a>  CArchive::operator &lt;&lt;  
 指定したオブジェクトまたはプリミティブ型、アーカイブを格納します。  
  
```  
friend CArchive& operator<<(
    CArchive& ar,  
    const CObject* pOb);

 
throw(
    CArchiveException*, 
    CFileException*);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator<<(
    const ATL::CStringT<BaseType,  
    StringTraits>& str);  
  
CArchive& operator<<(BYTE by); 
CArchive& operator<<(WORD w); 
CArchive& operator<<(LONG l); 
CArchive& operator<<(DWORD dw); 
CArchive& operator<<(float f); 
CArchive& operator<<(double d); 
CArchive& operator<<(int i); 
CArchive& operator<<(short w); 
CArchive& operator<<(char ch); 
CArchive& operator<<(wchar_t ch); 
CArchive& operator<<(unsigned u); 
CArchive& operator<<(bool b); 
CArchive& operator<<(ULONGLONG dwdw); 
CArchive& operator<<(LONGLONG dwdw);
```  
  
### <a name="return-value"></a>戻り値  
 A`CArchive`を 1 行に複数の挿入演算子を有効にするための参照。  
  
### <a name="remarks"></a>Remarks  
 上記の最後の 2 つのバージョンは、64 ビット整数値を格納するための特別なです。  
  
 実装では、クラス、IMPLEMENT_SERIAL マクロを使用するかどうかは、オーバー ロードされた挿入演算子`CObject`、保護された呼び出し`WriteObject`です。 この関数を呼び出す、`Serialize`クラスの関数。  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)挿入演算子 (<<) 診断ダンプとアーカイブへの格納をサポートしています。  
  
### <a name="example"></a>例  
 この例での使用、`CArchive`挿入演算子 << で、 **int**と**長い**型です。  
  
 [!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>例  
 この例 2 での`CArchive`挿入演算子 << で、`CStringT`型です。  
  
 [!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]  
  
##  <a name="operator_gt_gt"></a>  CArchive::operator &gt;&gt;  
 アーカイブから指定したオブジェクトまたはプリミティブ型を読み込みます。  
  
```  
friend CArchive& operator>>(
    CArchive& ar,  
    CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
friend CArchive& operator>>(
    CArchive& ar,  
    const CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator>>(
    ATL::CStringT<BaseType, 
    StringTraits>& str);  
  
CArchive& operator>>(BYTE& by);    
CArchive& operator>>(WORD& w);    
CArchive& operator>>(int& i);    
CArchive& operator>>(LONG& l);    
CArchive& operator>>(DWORD& dw);    
CArchive& operator>>(float& f);    
CArchive& operator>>(double& d);    
CArchive& operator>>(short& w);    
CArchive& operator>>(char& ch);    
CArchive& operator>>(wchar_t& ch);    
CArchive& operator>>(unsigned& u);    
CArchive& operator>>(bool& b);    
CArchive& operator>>(ULONGLONG& dwdw);   
CArchive& operator>>(LONGLONG& dwdw);
```  
  
### <a name="return-value"></a>戻り値  
 A`CArchive`を 1 行に複数の抽出演算子を有効にするための参照。  
  
### <a name="remarks"></a>Remarks  
 上記の最後の 2 つのバージョンは、64 ビット整数値を読み込むための特別なです。  
  
 実装では、クラス、IMPLEMENT_SERIAL マクロを使用するかどうか、抽出演算子をオーバー ロードの`CObject`、保護された呼び出し`ReadObject`(0 以外のランタイム クラスのポインター) を持つ関数です。 この関数を呼び出す、`Serialize`クラスの関数。  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)抽出演算子 (>>) アーカイブからの読み込みをサポートしています。  
  
### <a name="example"></a>例  
 この例での使用、`CArchive`抽出演算子 >> で、 **int**型です。  
  
 [!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>例  
 この例での使用、`CArchive`挿入と抽出演算子 <\<と >> で、`CStringT`型です。  
  
 [!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="read"></a>  読み書きするとき  
 アーカイブから指定したバイト数を読み取ります。  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 アーカイブから読み取られるデータを受信するユーザーが指定したバッファーへのポインター。  
  
 *nMax*  
 アーカイブから読み取られるバイト数を指定する符号なし整数。  
  
### <a name="return-value"></a>戻り値  
 実際に読み取られたバイト数を表す符号なし整数。 戻り値が、要求された数よりも小さい場合は、ファイルの末尾に到達しました。 ファイルの終了条件には、例外はスローされません。  
  
### <a name="remarks"></a>Remarks  
 アーカイブは、バイト数を解釈できません。  
  
 使用することができます、`Read`内でメンバー関数、`Serialize`オブジェクトに含まれている通常の構造を読み取るための関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="readclass"></a>  場合  
 このメンバー関数で格納されていたクラスへの参照を読み取る[WriteClass](#writeclass)です。  
  
```  
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,  
    UINT* pSchema = NULL,  
    DWORD* pObTag = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pClassRefRequested*  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)要求クラスの参照に対応する構造体。 指定できます**NULL**です。  
  
 *pSchema*  
 以前に格納されているランタイム クラスのスキーマへのポインター。  
  
 *pObTag*  
 オブジェクトの一意のタグを表す数値。 実装で内部的に使用される[ReadObject](#readobject)です。 高度なプログラミングだけです。*pObTag*通常する必要があります**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体。  
  
### <a name="remarks"></a>Remarks  
 場合*pClassRefRequested*は**NULL**、`ReadClass`アーカイブされたクラスの情報がランタイム クラスに互換性があることを確認します。 場合は、互換性がありません`ReadClass`がスローされます、 [CArchiveException](../../mfc/reference/carchiveexception-class.md)です。  
  
 ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)、それ以外の`ReadClass`がスローされます、[行わない](../../mfc/reference/cnotsupportedexception-class.md)です。  
  
 場合*pSchema*は**NULL**を呼び出してストアド クラスのスキーマを取得できる[CArchive::GetObjectSchema](#getobjectschema)以外の場合、**\** * *pSchema*は保存されていたランタイム クラスのスキーマが含まれます。  
  
 使用することができます[SerializeClass](#serializeclass)の代わりに`ReadClass`、両方の読み取りと書き込みクラスの参照を処理します。  
  
### <a name="example"></a>例  
  例を参照して[CArchive::WriteClass](#writeclass)です。  
  
##  <a name="readobject"></a>  CArchive::ReadObject  
 アーカイブからオブジェクト データを読み込んで、適切な型のオブジェクトを構築します。  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>パラメーター  
 *pClass*  
 定数ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)を読み込む予定がオブジェクトに対応する構造体。  
  
### <a name="return-value"></a>戻り値  
 A [CObject](../../mfc/reference/cobject-class.md)を使用して派生クラスを適切に安全にキャストする必要がありますポインター[使うため](../../mfc/reference/cobject-class.md#iskindof)です。  
  
### <a name="remarks"></a>Remarks  
 この関数は通常、呼び出される、`CArchive`抽出 ( **>>**) のオーバー ロードされた演算子、 [CObject](../../mfc/reference/cobject-class.md)ポインター。 `ReadObject`、、さらに、`Serialize`アーカイブ済みのクラスの関数。  
  
 0 以外を指定する場合*pClass*ことによって取得されるパラメーター、 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロ、関数は、アーカイブ済みのオブジェクトのランタイム クラスをことを確認します。 これには、クラスの実装で IMPLEMENT_SERIAL マクロを使用した前提としています。  
  
### <a name="example"></a>例  
  例を参照して[CArchive::WriteObject](#writeobject)です。  
  
##  <a name="readstring"></a>  CArchive::ReadString  
 関連付けられているファイルからバッファーにテキスト データを読み取るには、このメンバー関数を呼び出す、`CArchive`オブジェクト。  
  
```  
BOOL ReadString(CString& rString); 
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *rString*  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md) CArchive オブジェクトに関連付けられているファイルから読み取られた後、結果の文字列が含まれる。  
  
 *lpsz*  
 Null で終わる文字列を受信するユーザーが指定したバッファーへのポインターを指定します。  
  
 *nMax*  
 読み取る文字の最大数を指定します。 いずれかを指定する必要がありますのサイズよりも小さいか、 *lpsz*バッファー。  
  
### <a name="return-value"></a>戻り値  
 取得するバージョンで**BOOL**、 **TRUE**成功した場合**FALSE**それ以外の場合。  
  
 取得するバージョンでは、 `LPTSTR`、テキスト データを格納するバッファーへのポインター**NULL**ファイルの終端に達した場合。  
  
### <a name="remarks"></a>Remarks  
 メンバー関数のバージョンで、 *nMax*パラメーター、バッファーを保持する制限する*nMax* - 1 文字です。 キャリッジ リターンとライン フィードのペアによって、読み込みは停止します。 後続の改行文字は常に削除します。 どちらの場合は、null 文字 ('\0') が追加されます。  
  
 [読み書きするとき](#read)はキャリッジ リターンとライン フィードのペアに対してがテキスト モードの入力を終了しないにも使用できます。  
  
### <a name="example"></a>例  
  例を参照して[CArchive::WriteString](#writestring)です。  
  
##  <a name="serializeclass"></a>  CArchive::SerializeClass  
 格納し、基本クラスのバージョン情報を読み込む場合は、このメンバー関数を呼び出します。  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>パラメーター  
 *pClassRef*  
 基本クラスのランタイム クラス オブジェクトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 `SerializeClass` 読み取りまたは書き込みをクラスへの参照、`CArchive`の方向に応じて、オブジェクト、`CArchive`です。 使用して`SerializeClass`の代わりに[ReadClass](#readclass)と[WriteClass](#writeclass)基底クラスのオブジェクトをシリアル化する便利な手段として`SerializeClass`少ないコードと数のパラメーターが必要です。  
  
 同様に`ReadClass`、`SerializeClass`アーカイブされたクラスの情報がランタイム クラスに互換性があることを確認します。 場合は、互換性がありません`SerializeClass`がスローされます、 [CArchiveException](../../mfc/reference/carchiveexception-class.md)です。  
  
 ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)、それ以外の`SerializeClass`がスローされます、[行わない](../../mfc/reference/cnotsupportedexception-class.md)です。  
  
 使用して、 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロの値を取得する、 *pRuntimeClass*パラメーター。 基本クラスを使用する必要がありますが、 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="setloadparams"></a>  CArchive::SetLoadParams  
 呼び出す`SetLoadParams`ときしようとする読み取りの数が多い`CObject`-アーカイブから派生したオブジェクト。  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>パラメーター  
 *nGrowBy*  
 サイズの増加が必要な場合を確保する要素のスロットの最小数。  
  
### <a name="remarks"></a>Remarks  
 `CArchive` アーカイブに格納されているオブジェクトへの参照を解決するのには、負荷の配列を使用します。 `SetLoadParams` 使用すると、ロード配列を拡張するサイズを設定できます。  
  
 呼び出す必要はありません`SetLoadParams`任意のオブジェクトが読み込まれた後、または後[MapObject](#mapobject)または[ReadObject](#readobject)と呼びます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="setobjectschema"></a>  CArchive::SetObjectSchema  
 アーカイブ オブジェクトに格納されているオブジェクトのスキーマを設定するには、このメンバー関数を呼び出す*nSchema*です。  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSchema*  
 オブジェクトのスキーマを指定します。  
  
### <a name="remarks"></a>Remarks  
 次に呼び出した[使い方](#getobjectschema)に格納されている値が返されます*nSchema*です。  
  
 使用して`SetObjectSchema`の高度なバージョン管理します。 たとえば、とを適用するで読み取られる特定のバージョン、`Serialize`派生クラスの関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="setstoreparams"></a>  CArchive::SetStoreParams  
 使用して`SetStoreParams`大きな数を格納するときに`CObject`-アーカイブ内のオブジェクトを派生します。  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>パラメーター  
 *nHashSize*  
 インターフェイス ポインターのハッシュ テーブルのサイズにマップします。 素数をする必要があります。  
  
 *nBlockSize*  
 パラメーターを拡張するためのメモリ割り当ての粒度を指定します。 最適なパフォーマンスを 2 の累乗にする必要があります。  
  
### <a name="remarks"></a>Remarks  
 `SetStoreParams` ハッシュ テーブルのサイズと、シリアル化プロセス中に一意のオブジェクトを識別するために使用するマップのブロック サイズを設定できます。  
  
 呼び出す必要はありません`SetStoreParams`任意のオブジェクトが格納された、または後[MapObject](#mapobject)または[WriteObject](#writeobject)と呼びます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="write"></a>  CArchive::Write  
 指定したバイト数をアーカイブに書き込みます。  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuf*  
 アーカイブに書き込まれるデータを格納しているユーザーが指定したバッファーへのポインター。  
  
 *nMax*  
 アーカイブに書き込まれるバイト数を指定する整数。  
  
### <a name="remarks"></a>Remarks  
 アーカイブのバイトをフォーマットしません。  
  
 使用することができます、`Write`内でメンバー関数、`Serialize`通常構造を記述する関数は、オブジェクトに含まれます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="writeclass"></a>  CArchive::WriteClass  
 使用して`WriteClass`派生クラスのシリアル化中に基底クラスのバージョンとクラスの情報を格納します。  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>パラメーター  
 *pClassRef*  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)要求クラスの参照に対応する構造体。  
  
### <a name="remarks"></a>Remarks  
 `WriteClass` 参照を書き込みます、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 、基本クラスに対する、`CArchive`です。 使用して[場合](#readclass)への参照を取得します。  
  
 `WriteClass` アーカイブ済みのクラス情報にランタイム クラスに互換性があることを確認します。 場合は、互換性がありません`WriteClass`がスローされます、 [CArchiveException](../../mfc/reference/carchiveexception-class.md)です。  
  
 ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)、それ以外の`WriteClass`がスローされます、[行わない](../../mfc/reference/cnotsupportedexception-class.md)です。  
  
 使用することができます[SerializeClass](#serializeclass)の代わりに`WriteClass`、両方の読み取りと書き込みクラスの参照を処理します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]  
  
##  <a name="writeobject"></a>  CArchive::WriteObject  
 指定した格納`CObject`アーカイブにします。  
  
```  
void WriteObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>パラメーター  
 *私書箱*  
 格納されているオブジェクトへの定数ポインター。  
  
### <a name="remarks"></a>Remarks  
 この関数は通常、呼び出される、`CArchive`挿入 ( **<<**) の演算子はオーバー ロード`CObject`です。 `WriteObject`、、さらに、`Serialize`アーカイブ済みのクラスの関数。  
  
 使用する必要があります、`IMPLEMENT_SERIAL`マクロ アーカイブを有効にします。 `WriteObject` アーカイブするには、ASCII クラス名を書き込みます。 このクラス名が、読み込みプロセス中に後で検証されます。 特殊なエンコード スキームでは、クラスの複数のオブジェクトのクラス名の不要な重複しないようにします。 このスキームでは、1 つ以上のポインターの対象になっているオブジェクトの冗長ストレージを防ぐことができます。  
  
 メソッド (ASCII クラス名の有無を含む) をエンコード、正確なオブジェクトは、実装の詳細し、後で、ライブラリのバージョンで変更できます。  
  
> [!NOTE]
>  作成、削除、およびアーカイブして開始する前に、すべてのオブジェクトの更新を完了します。 アーカイブ オブジェクトの変更とを混在している場合、アーカイブは破損しています。  
  
### <a name="example"></a>例  
 クラスの定義の`CAge`の例を参照して[使われて](../../mfc/reference/coblist-class.md#coblist)です。  
  
 [!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="writestring"></a>  CArchive::WriteString  
 このメンバー関数を使用してバッファーからデータを関連付けられたファイルを書き込む、`CArchive`オブジェクト。  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpsz*  
 Null で終わる文字列を格納するバッファーへのポインターを指定します。  
  
### <a name="remarks"></a>Remarks  
 終端の null 文字 ('\0') は、ファイルに書き込まれませんまた、改行を配置に自動的に書き込まれます。  
  
 `WriteString` ディスクの空き容量の条件を含む、いくつかの条件への応答で例外をスローします。  
  
 `Write` 利用できますが、要求されたバイト数、ファイルに書き込みますが、null 文字で終了してではなく、します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CSocket クラス](../../mfc/reference/csocket-class.md)   
 [CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
