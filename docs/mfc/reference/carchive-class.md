---
title: CArchive クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 8f169964c6a313f37b5ea50a5105af29af7b59b1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266329"
---
# <a name="carchive-class"></a>CArchive クラス

オブジェクトの複雑なネットワーク オブジェクトを削除した後が引き続き発生する永続的なバイナリ形式 (通常はディスク ストレージ) に保存することができます。

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
|[CArchive::Close](#close)|書き込まれていないデータをまとめてフラッシュし、切断、`CFile`します。|
|[ときは](#flush)|アーカイブのバッファーから書き込まれていないデータをフラッシュします。|
|[CArchive::GetFile](#getfile)|取得、`CFile`このアーカイブのオブジェクト ポインター。|
|[CArchive::GetObjectSchema](#getobjectschema)|呼び出される、`Serialize`逆シリアル化するオブジェクトのバージョンを判断する関数。|
|[CArchive::IsBufferEmpty](#isbufferempty)|Windows ソケットの中にバッファーを空になっていないかどうかを決定します。 プロセスを受信します。|
|[CArchive::IsLoading](#isloading)|アーカイブが読み込み中かどうかを判断します。|
|[CArchive::IsStoring](#isstoring)|アーカイブを格納するかどうかを判断します。|
|[CArchive::MapObject](#mapobject)|ファイルにシリアル化されませんが、参照のサブオブジェクトとして入手可能なマップ内のオブジェクトを配置します。|
|[CArchive::Read](#read)|生のバイトを読み取ります。|
|[CArchive::ReadClass](#readclass)|クラスの参照が以前に格納されている読み取り`WriteClass`します。|
|[CArchive::ReadObject](#readobject)|オブジェクトの呼び出し`Serialize`読み込み関数。|
|[CArchive::ReadString](#readstring)|1 行のテキストを読み取ります。|
|[CArchive::SerializeClass](#serializeclass)|読み取りまたは書き込みへの参照をクラス、`CArchive`オブジェクトの方向に応じて、`CArchive`します。|
|[CArchive::SetLoadParams](#setloadparams)|ロード配列を拡張するサイズを設定します。 任意のオブジェクトが読み込まれる前に、または前に呼び出す必要があります`MapObject`または`ReadObject`が呼び出されます。|
|[CArchive::SetObjectSchema](#setobjectschema)|アーカイブ オブジェクトに格納されているオブジェクトのスキーマを設定します。|
|[CArchive::SetStoreParams](#setstoreparams)|ハッシュ テーブルのサイズと、シリアル化プロセス中に一意のオブジェクトを識別するために使用するマップのブロック サイズを設定します。|
|[CArchive::Write](#write)|生のバイトを書き込みます。|
|[CArchive::WriteClass](#writeclass)|参照を書き込みます、`CRuntimeClass`を`CArchive`します。|
|[CArchive::WriteObject](#writeobject)|オブジェクトの呼び出し`Serialize`を格納するための関数。|
|[CArchive::WriteString](#writestring)|1 行のテキストを書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CArchive::operator &lt;&lt;](#operator_lt_lt)|オブジェクトとプリミティブ型、アーカイブに格納されます。|
|[CArchive::operator &gt;&gt;](#operator_gt_gt)|アーカイブからのオブジェクト、プリミティブ型を読み込みます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CArchive::m_pDocument](#m_pdocument)||

## <a name="remarks"></a>Remarks

`CArchive` 基本クラスはありません。

後でメモリに保持して再構築の永続ストレージからオブジェクトを読み込むことができます。 データを永続的なは、このプロセスは「シリアル化します」と呼ばれる

アーカイブ オブジェクトをバイナリ ストリームの一種として考えることができます。 入力/出力ストリームのようにアーカイブがファイルに関連付けられ、バッファー内の書き込みと storage との間のデータの読み取りを許可します。 入力/出力ストリームは、ASCII 文字のシーケンスを処理しますが、アーカイブ、非冗長の効率的な形式でバイナリ オブジェクトのデータを処理します。

作成する必要があります、 [CFile](../../mfc/reference/cfile-class.md)オブジェクトを作成する前に、`CArchive`オブジェクト。 さらに、アーカイブの読み込み/ストアの状態がファイルのオープン モードと互換性があることを確認する必要があります。 1 つのアクティブなアーカイブ ファイルごとに制限されます。

構築する際に、`CArchive`オブジェクト、クラスのオブジェクトにアタッチする`CFile`(または派生クラス) を開いているファイルを表します。 また、アーカイブを読み込んだり格納したりするのに使用するかも指定します。 A`CArchive`プリミティブ型だけでなく、オブジェクトのオブジェクトが処理できる[CObject](../../mfc/reference/cobject-class.md)の派生クラスのシリアル化のために設計されています。 シリアル化可能なクラスは、通常、`Serialize`メンバー関数、およびそれが通常使用して、 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロ、クラスの下の説明に従って`CObject`します。

オーバー ロードされた抽出 ( **>>**) と挿入 ( **<<**) 演算子は、両方のプリミティブ型をサポートする便利なアーカイブ プログラミング インターフェイスと`CObject`-クラスを派生します。

`CArchive` Windows ソケットの MFC クラスを使用したプログラミングにもサポート[CSocket](../../mfc/reference/csocket-class.md)と[CSocketFile](../../mfc/reference/csocketfile-class.md)します。 [時](#isbufferempty)メンバー関数は、その使用状況をサポートしています。

詳細については`CArchive`、記事を参照して[シリアル化](../../mfc/serialization-in-mfc.md)と[Windows ソケット。アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。

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

`CArchive`は通常はデストラクターを呼び出す`Close`、保存されていないすべてのデータをフラッシュするが、関連付けられている`CFile`オブジェクト。 これにより、例外が発生します。

使用することをお勧めはこれらの例外をキャッチするときに`Abort`、破棄されるように、`CArchive`オブジェクトな例外が発生します。 例外を処理するときに`CArchive::Abort`ために、エラーに例外をスローしませんとは異なり、 [CArchive::Close](#close)、`Abort`エラーは無視されます。

使用した場合**新しい**を割り当てる、`CArchive`ヒープのオブジェクト ファイルを閉じて後に削除する必要があります。

### <a name="example"></a>例

  例をご覧ください[CArchive::WriteClass](#writeclass)します。

##  <a name="carchive"></a>  CArchive::CArchive

構築、`CArchive`オブジェクトし、の読み込みやオブジェクトを格納する使用するかどうかを指定します。

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>パラメーター

*pFile*<br/>
ポインター、 `CFile` ultimate ソースまたは永続的なデータのコピー先であるオブジェクト。

*nMode*<br/>
オブジェクトがから読み込まれたか、アーカイブに格納されているかどうかを指定するフラグ。 *NMode*パラメーターは、次の値のいずれかでなければなりません。

- `CArchive::load` アーカイブからデータを読み込みます。 必要なだけです`CFile`読み取りアクセス許可。

- `CArchive::store` データをアーカイブに保存します。 必要があります`CFile`書き込みアクセス許可。

- `CArchive::bNoFlushOnDelete` アーカイブが自動的に呼び出すことを防ぎます`Flush`アーカイブ デストラクターが呼び出された場合。 このフラグを設定した場合は明示的に呼び出す必要`Close`デストラクターが呼び出される前にします。 そうでない場合、データが破損します。

*nBufSize*<br/>
内部ファイル バッファーのサイズをバイト単位で示す整数。 既定のバッファー サイズは 4,096 バイトであることに注意してください。 ラージ オブジェクトを定期的にアーカイブする場合、ファイルのバッファー サイズの倍数である大きなバッファー サイズを使用する場合、パフォーマンスが向上します。

*lpBuf*<br/>
ポインターで、ユーザーが指定したサイズのバッファーを*nBufSize*します。 このパラメーターを指定しない場合、アーカイブはローカル ヒープからバッファーを割り当て、オブジェクトが破棄されるときに、それを解放します。 アーカイブは、ユーザーが指定したバッファーを解放しません。

### <a name="remarks"></a>Remarks

アーカイブを作成した後、この仕様を変更することはできません。

使用することは`CFile`アーカイブを終了するまで、ファイルの状態を変更する操作。 このような操作には、アーカイブの整合性が破損します。 シリアル化中にいつでもからアーカイブのファイル オブジェクトを取得することにより、ファイル ポインターの位置をアクセスする可能性があります、 [GetFile](#getfile)メンバー関数を使用して、[実行](../../mfc/reference/cfile-class.md#getposition)関数. 呼び出す必要があります[ときは](#flush)ファイル ポインターの位置を取得する前にします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

##  <a name="close"></a>  CArchive::Close

バッファーに残っているすべてのデータをフラッシュ、アーカイブ、閉じて、ファイルから、アーカイブを切断します。

```
void Close();
```

### <a name="remarks"></a>Remarks

アーカイブで他の操作が許可されていません。 アーカイブを閉じた後、同じファイルに対して別のアーカイブを作成またはファイルを閉じることができます。

メンバー関数は、`Close`により、ファイルをアーカイブからすべてのデータを転送し、アーカイブを使用できなくなります。 ストレージ メディアには、ファイルからの転送を完了する必要があります最初に使用する[データ](../../mfc/reference/cfile-class.md#close)し、破棄、`CFile`オブジェクト。

### <a name="example"></a>例

  例をご覧ください[CArchive::WriteString](#writestring)します。

##  <a name="flush"></a>  ときは

アーカイブ ファイルに書き込まれるバッファーの残りの部分を強制します。

```
void Flush();
```

### <a name="remarks"></a>Remarks

メンバー関数は、`Flush`にすべてのデータは、ファイルをアーカイブからに転送できます。 呼び出す必要があります[データ](../../mfc/reference/cfile-class.md#close)ストレージ メディアには、ファイルからの転送を完了します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

##  <a name="getfile"></a>  CArchive::GetFile

取得、`CFile`このアーカイブのオブジェクト ポインター。

```
CFile* GetFile() const;
```

### <a name="return-value"></a>戻り値

定数ポインター、`CFile`使用中のオブジェクト。

### <a name="remarks"></a>Remarks

使用する前に、アーカイブをフラッシュする必要があります`GetFile`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

##  <a name="getobjectschema"></a>  CArchive::GetObjectSchema

この関数から呼び出す、`Serialize`現在逆シリアル化するオブジェクトのバージョンを判断する関数。

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>戻り値

逆シリアル化は、読み取られているオブジェクトのバージョン。

### <a name="remarks"></a>Remarks

この関数を呼び出す場合のみを有効な`CArchive`オブジェクトが読み込まれている ([場合](#isloading)0 以外の値を返します)。 最初の呼び出しで必要がある、`Serialize`関数と呼び出し先の 1 回だけです。 (UINT)-1 の戻り値は、バージョン番号が不明であることを示します。

A `CObject`-派生クラスを使用して組み合わせる VERSIONABLE_SCHEMA、可能性があります (ビット演算子を使用して**または**) (IMPLEMENT_SERIAL マクロ) にあるスキーマ バージョン自体とオブジェクトを作成する"にバージョン管理、"オブジェクトは、ある`Serialize`メンバー関数は、複数のバージョンを読み取ることができます。 VERSIONABLE_SCHEMA) (なし、既定のフレームワーク機能では、バージョンが一致しないときに例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

##  <a name="isbufferempty"></a>  CArchive::IsBufferEmpty

アーカイブ オブジェクトの内部バッファーが空かどうかを判断するには、このメンバー関数を呼び出します。

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>戻り値

アーカイブのバッファーが空である場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

MFC Windows Sockets クラスを使用したプログラミングをサポートするためにこの関数に渡された`CSocketFile`します。 関連付けられているアーカイブに使用する必要はありません、`CFile`オブジェクト。

使用する理由`IsBufferEmpty`に関連付けられているアーカイブを使用して、`CSocketFile`オブジェクトは、アーカイブのバッファーにが 1 つ以上のメッセージまたはレコードに含まれます。 1 つのメッセージを受信するには、後に使用する必要があります`IsBufferEmpty`バッファーが空になるまでデータの受信を継続するループを制御します。 詳細については、、[受信](../../mfc/reference/casyncsocket-class.md#receive)クラスのメンバー関数`CAsyncSocket`、使用する方法を示す`IsBufferEmpty`を参照してください。

詳細については、次を参照してください。 [Windows ソケット。アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)します。

##  <a name="isloading"></a>  CArchive::IsLoading

アーカイブはデータを読み込むかどうかを判断します。

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>戻り値

アーカイブが現在読み込み用に使用されている場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数を呼び出して、`Serialize`アーカイブ済みのクラスの関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

##  <a name="isstoring"></a>  CArchive::IsStoring

アーカイブがデータを格納するかどうかを判断します。

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>戻り値

アーカイブが現在; を格納するために使用されている場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数を呼び出して、`Serialize`アーカイブ済みのクラスの関数。

場合、`IsStoring`アーカイブの状態が 0 以外の場合、その`IsLoading`状態は 0 です。 その逆です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

##  <a name="mapobject"></a>  CArchive::MapObject

実際に、ファイルにシリアル化されませんマップ内のオブジェクトを配置するには、このメンバー関数を呼び出すが、参照のサブオブジェクトとして提供されます。

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>パラメーター

*私書箱*<br/>
格納されているオブジェクトへの定数のポインター。

### <a name="remarks"></a>Remarks

たとえば、ドキュメントをシリアル化しない可能性がありますが、ドキュメントの一部である項目をシリアル化する場合します。 呼び出して`MapObject`、これらの項目、またはサブオブジェクトは、ドキュメントを参照することができます。 また、シリアル化されたサブ項目をシリアル化できる、 *m_pDocument*バック ポインター。

呼び出すことができます`MapObject`に格納しからの読み込み、`CArchive`オブジェクト。 `MapObject` 指定したオブジェクトによって保持される内部データ構造を追加します、`CArchive`オブジェクトとは異なりが、シリアル化および逆シリアル化中に[ReadObject](#readobject)と[WriteObject](#writeobject)は呼び出しませんオブジェクトのシリアル化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

##  <a name="m_pdocument"></a>  CArchive::m_pDocument

既定でこのポインターを NULL に設定、`CDocument`のユーザーに何かに設定できます、`CArchive`がのインスタンスします。

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>Remarks

This ポインターの一般的な使用方法は、シリアル化されているすべてのオブジェクトにシリアル化プロセスに関する追加情報を伝達するためには。 これは、ドキュメントにポインターを初期化することによって実現されます (、 `CDocument`-派生クラス) をシリアル化される、必要な場合に、ドキュメント内のオブジェクトがドキュメントをアクセスできるようにします。 このポインターはによっても使用`COleClientItem`オブジェクトをシリアル化中にします。

Framework セット*m_pDocument*ユーザーがファイルを発行するときにシリアル化されているドキュメントを開くか、コマンドを保存します。 明示的に設定する必要がある場合は、Object Linking and Embedding (OLE) コンテナーのドキュメント ファイルを開くまたは保存以外の理由をシリアル化する*m_pDocument*します。 たとえばはこれを行うをクリップボードにコンテナーのドキュメントをシリアル化するとします。

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

A`CArchive`により、1 行に複数の挿入演算子の参照。

### <a name="remarks"></a>Remarks

上記の最後の 2 つのバージョンでは、具体的には、64 ビット整数を格納するのです。

IMPLEMENT_SERIAL マクロをクラスの実装で使用した場合のオーバー ロードされた挿入演算子`CObject`、保護された呼び出し`WriteObject`します。 さらに、この関数を呼び出す、`Serialize`クラスの関数。

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)挿入演算子 (<<) 診断ダンプとアーカイブへの格納をサポートしています。

### <a name="example"></a>例

この例の使用、`CArchive`挿入演算子 << で、 **int**と**長い**型。

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>例

この例 2 の使用を示します、`CArchive`挿入演算子 << で、`CStringT`型。

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

A`CArchive`により、1 行に複数の抽出演算子の参照。

### <a name="remarks"></a>Remarks

上記の最後の 2 つのバージョンでは、64 ビット整数の読み込み専用のです。

IMPLEMENT_SERIAL マクロをクラスの実装で使用したかどうかは、抽出演算子のオーバー ロードされて`CObject`、保護された呼び出し`ReadObject`(0 以外の場合、ランタイム クラスのポインター) を持つ関数です。 さらに、この関数を呼び出す、`Serialize`クラスの関数。

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)抽出演算子 (>>) アーカイブからの読み込みをサポートしています。

### <a name="example"></a>例

この例の使用、`CArchive`抽出演算子 >> で、 **int**型。

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>例

この例の使用、`CArchive`挿入と抽出演算子 <\<と >> で、`CStringT`型。

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

##  <a name="read"></a>  CArchive::Read

アーカイブから指定したバイト数を読み取ります。

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
アーカイブから読み取られるデータを受信するユーザー指定のバッファーへのポインター。

*nMax*<br/>
アーカイブから読み取るバイト数を指定する符号なし整数。

### <a name="return-value"></a>戻り値

実際に読み取られたバイト数を含む符号なし整数。 戻り値が要求された数よりも小さい場合は、ファイルの末尾に達しています。 ファイルの終わり条件では、例外はスローされません。

### <a name="remarks"></a>Remarks

アーカイブのバイトを解釈しません。

使用することができます、`Read`内のメンバー関数、`Serialize`オブジェクトに含まれている通常の構造を読み取るための関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

##  <a name="readclass"></a>  CArchive::ReadClass

以前に格納されているクラスへの参照を読み取るには、このメンバー関数を呼び出す[WriteClass](#writeclass)します。

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>パラメーター

*pClassRefRequested*<br/>
ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)要求クラスの参照に対応する構造体。 NULL にすることができます。

*pSchema*<br/>
以前に格納されているランタイム クラスのスキーマへのポインター。

*pObTag*<br/>
オブジェクトの一意のタグを表す数値。 実装で内部的に使用される[ReadObject](#readobject)します。 高度なプログラミングだけです。*pObTag*通常 NULL にする必要があります。

### <a name="return-value"></a>戻り値

ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体。

### <a name="remarks"></a>Remarks

場合*pClassRefRequested*が NULL でない`ReadClass`アーカイブ済みのクラスの情報が、ランタイム クラスと互換性があることを確認します。 場合は、互換性がない`ReadClass`がスローされます、 [CArchiveException](../../mfc/reference/carchiveexception-class.md)します。

ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)、それ以外の`ReadClass`がスローされます、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)します。

場合*pSchema*が null の場合、ストアド クラスのスキーマを呼び出すことによって取得できる[CArchive::GetObjectSchema](#getobjectschema)、それ以外の<strong>\*</strong> *pSchema*は保存されていたランタイム クラスのスキーマが含まれます。

使用することができます[SerializeClass](#serializeclass)の代わりに`ReadClass`、読み取りと書き込みはクラス参照の両方を処理します。

### <a name="example"></a>例

  例をご覧ください[CArchive::WriteClass](#writeclass)します。

##  <a name="readobject"></a>  CArchive::ReadObject

アーカイブからオブジェクト データを読み取って、適切な型のオブジェクトを構築します。

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>パラメーター

*pClass*<br/>
定数ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)を読み込む予定がオブジェクトに対応する構造体。

### <a name="return-value"></a>戻り値

A [CObject](../../mfc/reference/cobject-class.md)は正しい、安全にキャストする必要がありますのポインターを使用してクラスを派生する[使うため](../../mfc/reference/cobject-class.md#iskindof)します。

### <a name="remarks"></a>Remarks

この関数は通常と呼ばれる、`CArchive`抽出 ( **>>**) の演算子はオーバー ロードを[CObject](../../mfc/reference/cobject-class.md)ポインター。 `ReadObject`を呼び出す、`Serialize`アーカイブ済みのクラスの関数。

0 以外を指定する場合*pClass*によって取得される、パラメーター、 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロ、関数は、アーカイブ済みのオブジェクトのランタイム クラスを確認します。 これにより、クラスの実装で IMPLEMENT_SERIAL マクロを使用したを前提としています。

### <a name="example"></a>例

  例をご覧ください[CArchive::WriteObject](#writeobject)します。

##  <a name="readstring"></a>  CArchive::ReadString

関連付けられているファイルからバッファーにテキスト データを読み込むには、このメンバー関数を呼び出す、`CArchive`オブジェクト。

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>パラメーター

*rString*<br/>
参照を[CString](../../atl-mfc-shared/reference/cstringt-class.md)は CArchive オブジェクトに関連付けられているファイルから読み取られた後、結果の文字列が含まれる。

*lpsz*<br/>
Null で終わる文字列を受け取るユーザーが指定したバッファーへのポインターを指定します。

*nMax*<br/>
読み取る文字の最大数を指定します。 1 つのサイズよりも小さいか、 *lpsz*バッファー。

### <a name="return-value"></a>戻り値

バージョンを返すブール値、成功した場合は TRUE。FALSE それ以外の場合。

返すバージョンで、 `LPTSTR`、テキスト データを格納しているバッファーへのポインターファイルの終わりに達した場合は NULL です。

### <a name="remarks"></a>Remarks

使用して、メンバー関数のバージョンで、 *nMax*パラメーター、バッファーを保持するに制限*nMax* - 1 文字。 キャリッジ リターンとラインフィードのペアによって、読み込みは停止します。 末尾の改行文字は常に削除します。 いずれの場合も、null 文字 ('\0') が追加されます。

[読み書きするとき](#read)はテキスト モードの入力が復帰と改行のペアで終了しないにも使用できます。

### <a name="example"></a>例

  例をご覧ください[CArchive::WriteString](#writestring)します。

##  <a name="serializeclass"></a>  CArchive::SerializeClass

基底クラスのバージョン情報に格納したりする場合に、このメンバー関数を呼び出します。

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>パラメーター

*pClassRef*<br/>
基本クラスのランタイム クラス オブジェクトへのポインター。

### <a name="remarks"></a>Remarks

`SerializeClass` 読み取りまたは書き込みするためのクラスへの参照、`CArchive`の方向に応じて、オブジェクト、`CArchive`します。 使用`SerializeClass`の代わりに[ReadClass](#readclass)と[WriteClass](#writeclass)基底クラスのオブジェクトをシリアル化する便利な方法として`SerializeClass`少ないコードとより少ないパラメーターが必要です。

ような`ReadClass`、`SerializeClass`アーカイブ済みのクラスの情報が、ランタイム クラスと互換性があることを確認します。 場合は、互換性がない`SerializeClass`がスローされます、 [CArchiveException](../../mfc/reference/carchiveexception-class.md)します。

ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)、それ以外の`SerializeClass`がスローされます、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)します。

使用して、 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロの値を取得、 *pRuntimeClass*パラメーター。 基本クラスを使用する必要がありますが、 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロ。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

##  <a name="setloadparams"></a>  CArchive::SetLoadParams

呼び出す`SetLoadParams`と読み取りの数が多いしようと`CObject`-アーカイブから派生したオブジェクト。

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>パラメーター

*nGrowBy*<br/>
サイズの増加が必要な場合に割り当てる要素のスロットの最小数。

### <a name="remarks"></a>Remarks

`CArchive` アーカイブに格納されているオブジェクトへの参照を解決するのには、負荷の配列を使用します。 `SetLoadParams` ロード配列を拡張するサイズを設定することができます。

呼び出す必要はありません`SetLoadParams`任意のオブジェクトが読み込まれた後、または後[MapObject](#mapobject)または[ReadObject](#readobject)が呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="setobjectschema"></a>  CArchive::SetObjectSchema

アーカイブ オブジェクトに格納されているオブジェクトのスキーマを設定するには、このメンバー関数を呼び出す*nSchema*します。

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>パラメーター

*nSchema*<br/>
オブジェクトのスキーマを指定します。

### <a name="remarks"></a>Remarks

次回の呼び出し[使い方](#getobjectschema)に格納されている値が返されます*nSchema*します。

使用`SetObjectSchema`の高度なバージョン管理。 たとえば、場合で読み取られる特定のバージョンを強制する、`Serialize`派生クラスの関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

##  <a name="setstoreparams"></a>  CArchive::SetStoreParams

使用`SetStoreParams`の数が多いを格納するときに`CObject`-アーカイブ内のオブジェクトを派生します。

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>パラメーター

*nHashSize*<br/>
インターフェイス ポインターのハッシュ テーブルのサイズにマップします。 素数にする必要があります。

*nBlockSize*<br/>
パラメーターを拡張するためのメモリ割り当ての粒度を指定します。 最適なパフォーマンス 2 のべき乗の必要があります。

### <a name="remarks"></a>Remarks

`SetStoreParams` ハッシュ テーブルのサイズと、シリアル化プロセス中に一意のオブジェクトを識別するために使用するマップのブロック サイズを設定することができます。

呼び出す必要はありません`SetStoreParams`後、すべてのオブジェクトが格納されている場合、または後[MapObject](#mapobject)または[WriteObject](#writeobject)が呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="write"></a>  CArchive::Write

指定したバイト数をアーカイブに書き込みます。

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
アーカイブに書き込まれるデータを格納するユーザーが指定したバッファーへのポインター。

*nMax*<br/>
アーカイブに書き込むバイト数を指定する整数。

### <a name="remarks"></a>Remarks

アーカイブのバイトをフォーマットしません。

使用することができます、`Write`内のメンバー関数、`Serialize`通常構造を記述する関数は、オブジェクトに含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

##  <a name="writeclass"></a>  CArchive::WriteClass

使用`WriteClass`派生クラスのシリアル化中に基底クラスのバージョンとクラス情報を格納します。

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>パラメーター

*pClassRef*<br/>
ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)要求クラスの参照に対応する構造体。

### <a name="remarks"></a>Remarks

`WriteClass` 参照を書き込みます、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 、基本クラスに対する、`CArchive`します。 使用[場合](#readclass)参照を取得します。

`WriteClass` アーカイブ済みのクラス情報に、ランタイム クラスと互換性があることを確認します。 場合は、互換性がない`WriteClass`がスローされます、 [CArchiveException](../../mfc/reference/carchiveexception-class.md)します。

ランタイム クラスを使用する必要があります[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)、それ以外の`WriteClass`がスローされます、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)します。

使用することができます[SerializeClass](#serializeclass)の代わりに`WriteClass`、読み取りと書き込みはクラス参照の両方を処理します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

##  <a name="writeobject"></a>  CArchive::WriteObject

指定した格納`CObject`をアーカイブします。

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>パラメーター

*私書箱*<br/>
格納されているオブジェクトへの定数のポインター。

### <a name="remarks"></a>Remarks

この関数は通常と呼ばれる、`CArchive`挿入 ( **<<**) の演算子はオーバー ロード`CObject`します。 `WriteObject`を呼び出す、`Serialize`アーカイブ済みのクラスの関数。

IMPLEMENT_SERIAL マクロを使用して、アーカイブを有効にする必要があります。 `WriteObject` アーカイブするには、ASCII クラス名を書き込みます。 読み込みプロセス中に後でこのクラス名が検証されます。 特殊なエンコード スキームでは、クラスの複数のオブジェクトのクラス名の不要な重複を防ぎます。 このスキームでは、1 つ以上のポインターの対象となるオブジェクトの冗長ストレージも回避されます。

エンコーディング (ASCII のクラス名の有無を含む) 方法、正確なオブジェクトでは、実装の詳細し、将来のバージョンのライブラリを変更できます。

> [!NOTE]
>  作成、削除、およびアーカイブすることで開始する前に、すべてのオブジェクトの更新を完了します。 オブジェクトの変更のアーカイブが混在する場合、アーカイブが壊れているがあります。

### <a name="example"></a>例

クラスの定義の`CAge`、例をご覧ください[使われて](../../mfc/reference/coblist-class.md#coblist)します。

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

##  <a name="writestring"></a>  CArchive::WriteString

このメンバー関数を使用してファイルに関連付けられているバッファーからデータを書き込む、`CArchive`オブジェクト。

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
Null で終わる文字列を格納するバッファーへのポインターを指定します。

### <a name="remarks"></a>Remarks

終端の null 文字 ('\0') は、ファイルに書き込まれませんまた、改行を自動的に書き込まれます。

`WriteString` ディスクの空き状況など、いくつかの条件に応答では、例外をスローします。

`Write` 使用ですが終了すると、null 文字ではなく、ファイルに要求されたバイト数を書き込みます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[CSocket クラス](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
