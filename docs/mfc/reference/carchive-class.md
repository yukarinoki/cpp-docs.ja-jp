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
ms.openlocfilehash: 46d30e38674d10aecdfdbf7be91c48063ba9f493
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377065"
---
# <a name="carchive-class"></a>CArchive クラス

オブジェクトが削除された後も永続バイナリ形式 (通常はディスク ストレージ) でオブジェクトの複雑なネットワークを保存できます。

## <a name="syntax"></a>構文

```
class CArchive
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[アーカイブ::Cアーカイブ](#carchive)|`CArchive` オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[アーカイブ::中止](#abort)|例外をスローせずにアーカイブを閉じます。|
|[アーカイブ::閉じる](#close)|書き込みされていないデータをフラッシュし、`CFile`から切断します。|
|[アーカイブ::フラッシュ](#flush)|アーカイブ バッファから未書き込みデータをフラッシュします。|
|[アーカイブ::ゲットファイル](#getfile)|このアーカイブ`CFile`のオブジェクト ポインターを取得します。|
|[オブジェクトスキーマを取得します。](#getobjectschema)|逆シリアル化`Serialize`されているオブジェクトのバージョンを確認するために、関数から呼び出されます。|
|[アーカイブ::IsBufferEmpty](#isbufferempty)|Windows ソケット受信プロセス中にバッファーが空になったかどうかを判断します。|
|[アーカイブ::イズローディング](#isloading)|アーカイブが読み込み中かどうかを判断します。|
|[アーカイブ::Is格納](#isstoring)|アーカイブが格納されているかどうかを判断します。|
|[アーカイブ::マップオブジェクト](#mapobject)|ファイルにシリアル化されていないが、サブオブジェクトが参照できるオブジェクトをマップに配置します。|
|[アーカイブ::読み取り](#read)|生バイトを読み取ります。|
|[アーカイブ::リードクラス](#readclass)|で以前に格納されたクラス参照`WriteClass`を読み取ります。|
|[アーカイブ::読み取りオブジェクト](#readobject)|読み込み用`Serialize`のオブジェクトの関数を呼び出します。|
|[アーカイブ::読み取り文字列](#readstring)|1 行のテキストを読み取ります。|
|[アーカイブ::シリアライズクラス](#serializeclass)|の方向に応じて、`CArchive`オブジェクトへのクラス参照を読み取るか`CArchive`書き込みます。|
|[アーカイブ::セットロードパラム](#setloadparams)|ロード配列のサイズを設定します。 オブジェクトがロードされる前、または呼び出`MapObject`される`ReadObject`前に呼び出される必要があります。|
|[アーカイブ::セットオブジェクトスキーマ](#setobjectschema)|アーカイブ オブジェクトに格納されているオブジェクト スキーマを設定します。|
|[アーカイブ::セットストアパラム](#setstoreparams)|シリアル化処理中に一意のオブジェクトを識別するために使用されるマップのハッシュ テーブル サイズとブロック サイズを設定します。|
|[アーカイブ::書き込み](#write)|生バイトを書き込みます。|
|[アーカイブ::書き込みクラス](#writeclass)|への参照を`CRuntimeClass`書き込みます`CArchive`。|
|[アーカイブ::オブジェクトの書き込み](#writeobject)|格納するオブジェクトの`Serialize`関数を呼び出します。|
|[アーカイブ::書き込み文字列](#writestring)|1 行のテキストを書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[アーカイブ::演算子&lt;&lt;](#operator_lt_lt)|オブジェクトとプリミティブ型をアーカイブに格納します。|
|[アーカイブ::演算子&gt;&gt;](#operator_gt_gt)|アーカイブからオブジェクトとプリミティブ型をロードします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[アーカイブ::m_pDocument](#m_pdocument)||

## <a name="remarks"></a>解説

`CArchive`は基本クラスを持っていません。

後で、永続ストレージからオブジェクトをロードして、それらをメモリに再構成することができます。 データを永続的にするこのプロセスは、"シリアル化" と呼ばれます。

アーカイブ オブジェクトは、バイナリ ストリームの一種と考えることができます。 入出力ストリームと同様に、アーカイブはファイルに関連付けられており、ストレージとの間でバッファされたデータの書き込みと読み取りを可能にします。 入出力ストリームは ASCII 文字のシーケンスを処理しますが、アーカイブはバイナリオブジェクトデータを効率的で非冗長形式で処理します。

オブジェクトを作成する前に[、CFile](../../mfc/reference/cfile-class.md)オブジェクトを`CArchive`作成する必要があります。 また、アーカイブのロード/ストアステータスがファイルのオープンモードと互換性があることを確認する必要があります。 ファイルごとにアクティブなアーカイブは 1 つに制限されます。

オブジェクトを`CArchive`構築する場合、開いているファイルを表すクラス`CFile`(または派生クラス) のオブジェクトにオブジェクトをアタッチします。 また、アーカイブをロードまたは保存に使用するかどうかも指定します。 オブジェクト`CArchive`は、プリミティブ型だけでなく、シリアル化用に設計された[CObject](../../mfc/reference/cobject-class.md)派生クラスのオブジェクトも処理できます。 通常、シリアル化可能なクラス`Serialize`にはメンバー関数があり、通常は[class](../../mfc/reference/run-time-object-model-services.md#declare_serial)`CObject`の下で説明するDECLARE_SERIALと[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを使用します。

オーバーロードされた抽出 ( **>>**) 演算子**<<** と挿入演算子 ( ) は、プリミティブ型と`CObject`派生クラスの両方をサポートする便利なアーカイブ プログラミング インターフェイスです。

`CArchive`また、MFC Windows ソケット クラス CSocket および[CSocketFile](../../mfc/reference/csocket-class.md)を使用したプログラミングもサポート[しています](../../mfc/reference/csocketfile-class.md)。 [メンバー](#isbufferempty)関数は、その使用方法をサポートしています。

の詳細については、「[シリアル化](../../mfc/serialization-in-mfc.md)と Windows[ソケット: アーカイブでのソケットの使用」を参照してください。](../../mfc/windows-sockets-using-sockets-with-archives.md) `CArchive`

## <a name="inheritance-hierarchy"></a>継承階層

`CArchive`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="carchiveabort"></a><a name="abort"></a>アーカイブ::中止

例外をスローせずにアーカイブを閉じます。

```
void Abort ();
```

### <a name="remarks"></a>解説

デス`CArchive`トラクターは通常、 を`Close`呼び出し、関連付けられた`CFile`オブジェクトに保存されていないデータをフラッシュします。 これにより、例外が発生する可能性があります。

これらの例外をキャッチする場合は、`Abort``CArchive`オブジェクトを破棄しても例外が発生しなくなるように、 を使用することをお勧めします。 例外を処理する場合`CArchive::Abort`[、CArchive::Close](#close)と`Abort`は異なり、エラーが無視されるため、エラーに対して例外はスローされません。

**new**を使用してヒープに`CArchive`オブジェクトを割り当てた場合は、ファイルを閉じた後で削除する必要があります。

### <a name="example"></a>例

  [「アーカイブ::書き込みクラス](#writeclass)」の例を参照してください。

## <a name="carchivecarchive"></a><a name="carchive"></a>アーカイブ::Cアーカイブ

オブジェクトを`CArchive`構築し、オブジェクトの読み込みまたは格納に使用するかどうかを指定します。

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>パラメーター

*ファイル*<br/>
永続データの`CFile`最終的なソースまたは宛先であるオブジェクトへのポインター。

*nモード*<br/>
オブジェクトをアーカイブから読み込むか、アーカイブに格納するかを指定するフラグ。 *nMode*パラメーターには、次のいずれかの値が必要です。

- `CArchive::load`アーカイブからデータを読み込みます。 読み`CFile`取りアクセス許可のみが必要です。

- `CArchive::store`アーカイブにデータを保存します。 書`CFile`き込み権限が必要です。

- `CArchive::bNoFlushOnDelete`アーカイブデストラクタが呼び`Flush`出されたときに、アーカイブが自動的に呼び出されないようにします。 このフラグを設定した場合、デストラクターが呼び出`Close`される前に明示的に呼び出す必要があります。 これを行わない場合、データが破損します。

*サイズを変更します。*<br/>
内部ファイル バッファーのサイズをバイト単位で指定する整数。 デフォルトのバッファ サイズは 4,096 バイトです。 大きなオブジェクトを定期的にアーカイブする場合は、ファイル・バッファー・サイズの倍数である大きなバッファー・サイズを使用すると、パフォーマンスが向上します。

*lpBuf*<br/>
サイズ*nBufSize*のユーザーが指定したバッファーへのポインター (省略可能) 。 このパラメーターを指定しない場合、アーカイブはローカル・ヒープからバッファーを割り振り、オブジェクトが破棄されるときに解放します。 アーカイブはユーザーが指定したバッファを解放しません。

### <a name="remarks"></a>解説

アーカイブを作成した後は、この仕様を変更できません。

アーカイブを閉じる`CFile`まで、操作を使用してファイルの状態を変更することはできません。 このような操作は、アーカイブの整合性を損ないます。 アーカイブのファイル オブジェクトを[GetFile](#getfile)メンバー関数から取得し[、CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition)関数を使用して、シリアル化中にいつでもファイル ポインターの位置にアクセスできます。 ファイル ポインタの位置を取得する前に[、CArchive::Flush](#flush)を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

## <a name="carchiveclose"></a><a name="close"></a>アーカイブ::閉じる

バッファーに残っているデータをフラッシュし、アーカイブを閉じ、アーカイブをファイルから切断します。

```
void Close();
```

### <a name="remarks"></a>解説

アーカイブに対するこれ以上の操作は許可されません。 アーカイブを閉じた後、同じファイルに対して別のアーカイブを作成するか、ファイルを閉じることができます。

メンバー関数`Close`は、すべてのデータがアーカイブからファイルに転送されることを保証し、アーカイブを使用できなくなります。 ファイルからストレージ メディアへの転送を完了するには、まず[CFile::Close](../../mfc/reference/cfile-class.md#close)を使用してからオブジェクトを破棄`CFile`する必要があります。

### <a name="example"></a>例

  [「アーカイブ::書き込み文字列](#writestring)」の例を参照してください。

## <a name="carchiveflush"></a><a name="flush"></a>アーカイブ::フラッシュ

アーカイブ バッファに残っているデータを強制的にファイルに書き込みます。

```
void Flush();
```

### <a name="remarks"></a>解説

メンバー関数`Flush`は、すべてのデータがアーカイブからファイルに転送されることを保証します。 [CFile::Close](../../mfc/reference/cfile-class.md#close)を呼び出して、ファイルからストレージ メディアへの転送を完了する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

## <a name="carchivegetfile"></a><a name="getfile"></a>アーカイブ::ゲットファイル

このアーカイブ`CFile`のオブジェクト ポインターを取得します。

```
CFile* GetFile() const;
```

### <a name="return-value"></a>戻り値

使用中の`CFile`オブジェクトへの定数ポインター。

### <a name="remarks"></a>解説

を使用`GetFile`する前にアーカイブをフラッシュする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

## <a name="carchivegetobjectschema"></a><a name="getobjectschema"></a>オブジェクトスキーマを取得します。

現在逆シリアル化されている`Serialize`オブジェクトのバージョンを確認するには、関数からこの関数を呼び出します。

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>戻り値

逆シリアル化中に、読み取られるオブジェクトのバージョン。

### <a name="remarks"></a>解説

この関数の呼び出しは`CArchive`、オブジェクトが読み込まれている場合にのみ有効です[(CArchive::IsLoading](#isloading)は 0 以外を返します)。 これは`Serialize`、関数の最初の呼び出しで、1 回だけ呼び出される必要があります。 (UINT)-1 の戻り値は、バージョン番号が不明であることを示します。

派生クラスは、スキーマ バージョン自体 (IMPLEMENT_SERIAL マクロ**内)** と組み合わせてVERSIONABLE_SCHEMAを使用して、メンバー関数が`Serialize`複数のバージョンを読み取ることができるオブジェクトを作成します。 `CObject` 既定のフレームワーク機能 (VERSIONABLE_SCHEMAなし) は、バージョンが一致しない場合に例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

## <a name="carchiveisbufferempty"></a><a name="isbufferempty"></a>アーカイブ::IsBufferEmpty

アーカイブ オブジェクトの内部バッファが空かどうかを確認します。

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>戻り値

アーカイブのバッファが空の場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、MFC Windows ソケット クラス`CSocketFile`を使用したプログラミングをサポートするために提供されます。 オブジェクトに関連付けられたアーカイブに使用する`CFile`必要はありません。

オブジェクトに関連付`IsBufferEmpty`けられたアーカイブで使用する理由は、アーカイブのバッファーに複数のメッセージまたはレコードが含まれる可能性があるためです。 `CSocketFile` 1 つのメッセージを受信した後`IsBufferEmpty`、バッファーが空になるまでデータの受信を続行するループを制御するために使用する必要があります。 詳細については、 クラスの[受信](../../mfc/reference/casyncsocket-class.md#receive)メンバー関数`CAsyncSocket`を参照`IsBufferEmpty`してください。

詳細については、「 [Windows ソケット : アーカイブでソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="carchiveisloading"></a><a name="isloading"></a>アーカイブ::イズローディング

アーカイブがデータを読み込み中かどうかを判断します。

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>戻り値

アーカイブが現在読み込み時に使用されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、アーカイブされた`Serialize`クラスの関数によって呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

## <a name="carchiveisstoring"></a><a name="isstoring"></a>アーカイブ::Is格納

アーカイブにデータが格納されているかどうかを判断します。

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>戻り値

アーカイブが現在格納に使用されている場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、アーカイブされた`Serialize`クラスの関数によって呼び出されます。

アーカイブの`IsStoring`ステータスが 0 以外の場合、その`IsLoading`ステータスは 0、その逆になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

## <a name="carchivemapobject"></a><a name="mapobject"></a>アーカイブ::マップオブジェクト

このメンバー関数を呼び出して、実際にはファイルにシリアル化されていないが、サブオブジェクトが参照できるオブジェクトをマップに配置します。

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>パラメーター

*Pob*<br/>
格納されているオブジェクトへの定数ポインター。

### <a name="remarks"></a>解説

たとえば、ドキュメントをシリアル化しない場合でも、ドキュメントの一部であるアイテムをシリアル化します。 を呼`MapObject`び出すと、それらのアイテムまたはサブオブジェクトがドキュメントを参照できるようになります。 また、シリアル化されたサブ項目は *、m_pDocument*の戻るポインターをシリアル化できます。

オブジェクトに対`MapObject`して保存および読み込みを行うときに呼び出すことができます。 `CArchive` `MapObject`シリアル化と逆シリアル化の間に`CArchive`オブジェクトが管理する内部データ構造に指定されたオブジェクトを追加しますが[、ReadObject](#readobject)や[WriteObject](#writeobject)とは異なり、オブジェクトのシリアル化は呼び出しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

## <a name="carchivem_pdocument"></a><a name="m_pdocument"></a>アーカイブ::m_pDocument

既定では NULL に設定され、この`CDocument`a へのポインターは`CArchive`、インスタンスのユーザーが望む何にでも設定できます。

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>解説

このポインターの一般的な使用方法は、シリアル化プロセスに関する追加情報をシリアル化されるすべてのオブジェクトに伝達することです。 これは、シリアル化されるドキュメント (`CDocument`派生クラス) を使用してポインタを初期化することで、ドキュメント内のオブジェクトが必要に応じてドキュメントにアクセスできるようにします。 このポインターは、シリアル化`COleClientItem`中にオブジェクトによっても使用されます。

ユーザーがファイルを開くまたは保存コマンドを発行すると、シリアル化されるドキュメントに*m_pDocument*を設定します。 ファイルを開くまたは保存以外の理由でオブジェクトのリンクと埋め込み (OLE) コンテナー ドキュメントをシリアル化する場合は、m_pDocument明示的*に設定する*必要があります。 たとえば、コンテナー ドキュメントをクリップボードにシリアル化する場合に、この操作を行います。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

## <a name="carchiveoperator-ltlt"></a><a name="operator_lt_lt"></a>アーカイブ::演算子&lt;&lt;

指定されたオブジェクトまたはプリミティブ型をアーカイブに格納します。

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

1`CArchive`行に複数の挿入演算子を使用できるようにする参照。

### <a name="remarks"></a>解説

上記の最後の 2 つのバージョンは、64 ビット整数を格納するためのものです。

クラスの実装で IMPLEMENT_SERIAL マクロを使用した場合、プロテクト`CObject``WriteObject`を呼び出す挿入演算子がオーバーロードされます。 この関数は、クラスの関数を`Serialize`呼び出します。

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)挿入演算子 (<<) は、診断ダンプとアーカイブへの格納をサポートします。

### <a name="example"></a>例

この例では、挿入演算子の使用方法`CArchive`を**int**型と**long**型で << します。

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>例

この例 2 では、型に`CArchive`対する挿入演算子 << `CStringT`の使用方法を示します。

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

## <a name="carchiveoperator-gtgt"></a><a name="operator_gt_gt"></a>アーカイブ::演算子&gt;&gt;

指定されたオブジェクトまたはプリミティブ型をアーカイブから読み込みます。

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

1`CArchive`行で複数の抽出演算子を使用できるようにする参照。

### <a name="remarks"></a>解説

上記の最後の 2 つのバージョンは、64 ビット整数を読み込む場合に特化したものです。

クラス実装でIMPLEMENT_SERIALマクロを使用した場合、抽出演算子はプロテクト`CObject``ReadObject`関数を呼び出す (0 以外のランタイム クラス ポインターを使用して) オーバーロードします。 この関数は、クラスの関数を`Serialize`呼び出します。

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)抽出演算子 (>>) は、アーカイブからの読み込みをサポートします。

### <a name="example"></a>例

この例では **、int**型`CArchive`で抽出演算子 >> を使用する方法を示します。

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>例

この例では、`CArchive`\<`CStringT`挿入演算子と抽出演算子を使用して、型と<し、型と >> を示します。

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

## <a name="carchiveread"></a><a name="read"></a>アーカイブ::読み取り

アーカイブから指定されたバイト数を読み取ります。

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
アーカイブから読み取られたデータを受け取るユーザー指定のバッファーへのポインター。

*nMax*<br/>
アーカイブから読み取るバイト数を指定する符号なし整数。

### <a name="return-value"></a>戻り値

実際に読み取られたバイト数を含む符号なし整数。 戻り値が要求された数より小さい場合は、ファイルの末尾に達しています。 ファイルの終わりの条件では例外はスローされません。

### <a name="remarks"></a>解説

アーカイブはバイトを解釈しません。

関数内でメンバー`Read`関数を使用して`Serialize`、オブジェクトに含まれる通常の構造体を読み取ることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

## <a name="carchivereadclass"></a><a name="readclass"></a>アーカイブ::リードクラス

[WriteClass](#writeclass)で以前に格納されたクラスへの参照を読み取るために、このメンバー関数を呼び出します。

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>パラメーター

*を要求しました。*<br/>
要求されたクラス参照に対応する[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。 NULL にすることができます。

*スキーマ*<br/>
以前に格納されたランタイム クラスのスキーマへのポインター。

*タグ*<br/>
オブジェクトの一意のタグを参照する番号。 [ReadObject](#readobject)の実装によって内部的に使用されます。 高度なプログラミングのためだけに公開されます。*pObTag は*通常 NULL にする必要があります。

### <a name="return-value"></a>戻り値

[構造体への](../../mfc/reference/cruntimeclass-structure.md)ポインター。

### <a name="remarks"></a>解説

*pClassRefRequested*が NULL`ReadClass`でない場合は、アーカイブされたクラス情報がランタイム クラスと互換性があることを確認します。 互換性がない場合は`ReadClass`[、CArchiveException](../../mfc/reference/carchiveexception-class.md)をスローします。

ランタイム クラスでは[、DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)を使用する必要があります。それ以外`ReadClass`の場合は[、CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)をスローします。

*pSchema*が NULL の場合は[、CArchive::GetObjectSchema](#getobjectschema)を呼び出すことによって、ストアド クラスのスキーマを取得できます。それ以外<strong>\*</strong>の場合 *、pSchema*には、以前に格納されたランタイム クラスのスキーマが含まれます。

の代わりに[SerializeClass](#serializeclass) `ReadClass`を使用して、クラス参照の読み取りと書き込みの両方を処理できます。

### <a name="example"></a>例

  [「アーカイブ::書き込みクラス](#writeclass)」の例を参照してください。

## <a name="carchivereadobject"></a><a name="readobject"></a>アーカイブ::読み取りオブジェクト

アーカイブからオブジェクト データを読み取り、適切な型のオブジェクトを構築します。

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>パラメーター

*Pclass*<br/>
読み取るオブジェクトに対応する[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体への定数ポインター。

### <a name="return-value"></a>戻り値

[CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)を使用して、正しい派生クラスに安全にキャストする必要がある CObject ポインター。 [CObject](../../mfc/reference/cobject-class.md)

### <a name="remarks"></a>解説

通常、この関数は[CObject](../../mfc/reference/cobject-class.md)ポインター**>>** に対して`CArchive`オーバーロードされた抽出 ( ) 演算子によって呼び出されます。 `ReadObject`を呼び出すと、`Serialize`アーカイブされたクラスの関数が呼び出されます。

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロによって取得される 0 以外の*pClass*パラメーターを指定した場合、関数はアーカイブされたオブジェクトの実行時クラスを検証します。 これは、クラスの実装でIMPLEMENT_SERIALマクロを使用していることを前提としています。

### <a name="example"></a>例

  [「アーカイブ::書き込みオブジェクト](#writeobject)」の例を参照してください。

## <a name="carchivereadstring"></a><a name="readstring"></a>アーカイブ::読み取り文字列

`CArchive`オブジェクトに関連付けられたファイルからテキスト データをバッファーに読み取ります。

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
CArchive オブジェクトに関連付けられたファイルから文字列を読み取った後に、その文字列を格納する[CString](../../atl-mfc-shared/reference/cstringt-class.md)への参照。

*lpsz*<br/>
null で終わるテキスト文字列を受け取るユーザー指定のバッファーへのポインターを指定します。

*nMax*<br/>
読み取る最大文字数を指定します。 *lpsz*バッファのサイズより 1 小さい値を指定してください。

### <a name="return-value"></a>戻り値

BOOL を返すバージョンでは、成功した場合は TRUE。それ以外の場合は FALSE。

を返すバージョンでは、`LPTSTR`テキスト データを格納しているバッファーへのポインター。ファイルの終わりに達した場合は NULL。

### <a name="remarks"></a>解説

*nMax*パラメーターを持つメンバー関数のバージョンでは、バッファーは*nMax* - 1 文字の制限まで保持します。 読み取りは、復帰線フィードのペアによって停止されます。 末尾の改行文字は常に削除されます。 いずれの場合も、NULL 文字 ('\0') が追加されます。

[CArchive::Read](#read)はテキスト モード入力でも使用できますが、復帰と改行のペアでは終了しません。

### <a name="example"></a>例

  [「アーカイブ::書き込み文字列](#writestring)」の例を参照してください。

## <a name="carchiveserializeclass"></a><a name="serializeclass"></a>アーカイブ::シリアライズクラス

基本クラスのバージョン情報を格納および読み込む場合に、このメンバー関数を呼び出します。

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>パラメーター

*クラス参照*<br/>
基本クラスのランタイム クラス オブジェクトへのポインター。

### <a name="remarks"></a>解説

`SerializeClass`の方向に応じて、`CArchive`オブジェクトへのクラスへの参照を読み取るか書き`CArchive`込みます。 基本`SerializeClass`クラスオブジェクトをシリアル化する便利な方法として[、ReadClass](#readclass)および[WriteClass](#writeclass)の代わりに使用します。`SerializeClass`必要なコードが少なく、パラメータも少なくなります。

同様`ReadClass`に`SerializeClass`、アーカイブされたクラス情報がランタイム クラスと互換性があることを確認します。 互換性がない場合は`SerializeClass`[、CArchiveException](../../mfc/reference/carchiveexception-class.md)をスローします。

ランタイム クラスでは[、DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)を使用する必要があります。それ以外`SerializeClass`の場合は[、CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)をスローします。

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロを使用して *、pRuntimeClass*パラメーターの値を取得します。 基本クラスは[、IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを使用している必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

## <a name="carchivesetloadparams"></a><a name="setloadparams"></a>アーカイブ::セットロードパラム

アーカイブ`SetLoadParams`から多数の`CObject`派生オブジェクトを読み取るときに呼び出します。

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>パラメーター

*nグローバイ*<br/>
サイズの増加が必要な場合に割り当てる要素スロットの最小数。

### <a name="remarks"></a>解説

`CArchive`では、ロード・アレイを使用して、アーカイブに保管されているオブジェクトへの参照を解決します。 `SetLoadParams`では、ロード・アレイのサイズを設定できます。

オブジェクトが読み`SetLoadParams`込まれた後、または MapObject または[ReadObject](#readobject)が呼び出された後は、呼び出しを行う必要があります。 [MapObject](#mapobject)

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivesetobjectschema"></a><a name="setobjectschema"></a>アーカイブ::セットオブジェクトスキーマ

アーカイブ オブジェクトに格納されているオブジェクト スキーマを*nSchema*に設定します。

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>パラメーター

*nスキーマ*<br/>
オブジェクトのスキーマを指定します。

### <a name="remarks"></a>解説

次の呼び出し[では](#getobjectschema)*、nSchema*に格納されている値が返されます。

高度`SetObjectSchema`なバージョン管理に使用します。たとえば、特定のバージョンを派生クラスの`Serialize`関数で強制的に読み取る場合などです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

## <a name="carchivesetstoreparams"></a><a name="setstoreparams"></a>アーカイブ::セットストアパラム

多数`SetStoreParams`の`CObject`派生オブジェクトをアーカイブに格納する場合に使用します。

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
インターフェイス ポインター マップのハッシュ テーブルのサイズ。 素数である必要があります。

*ブロックサイズ*<br/>
パラメーターを拡張するためのメモリ割り当ての粒度を指定します。 最高のパフォーマンスを得るための 2 の累乗である必要があります。

### <a name="remarks"></a>解説

`SetStoreParams`では、シリアル化プロセス中に一意のオブジェクトを識別するために使用されるマップのハッシュ テーブル サイズとブロック サイズを設定できます。

オブジェクトが格納された`SetStoreParams`後、または MapObject または[WriteObject](#mapobject)が呼び出された後は、呼び出してはなりません。 [WriteObject](#writeobject)

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivewrite"></a><a name="write"></a>アーカイブ::書き込み

指定したバイト数をアーカイブに書き込みます。

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
アーカイブに書き込まれるデータを格納するユーザーが指定したバッファーへのポインター。

*nMax*<br/>
アーカイブに書き込むバイト数を指定する整数。

### <a name="remarks"></a>解説

アーカイブはバイトをフォーマットしません。

関数内でメンバー`Write`関数を使用して、オブジェクトに含まれる通常の構造体を記述できます。 `Serialize`

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

## <a name="carchivewriteclass"></a><a name="writeclass"></a>アーカイブ::書き込みクラス

派生`WriteClass`クラスのシリアル化中に基本クラスのバージョン情報とクラス情報を格納するために使用します。

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>パラメーター

*クラス参照*<br/>
要求されたクラス参照に対応する[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。

### <a name="remarks"></a>解説

`WriteClass`基本クラスの[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)への参照を`CArchive`に書き込みます。 参照を取得するには[、CArchive::ReadClass](#readclass)を使用します。

`WriteClass`アーカイブされたクラス情報がランタイム クラスと互換性があることを確認します。 互換性がない場合は`WriteClass`[、CArchiveException](../../mfc/reference/carchiveexception-class.md)をスローします。

ランタイム クラスでは[、DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)を使用する必要があります。それ以外`WriteClass`の場合は[、CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)をスローします。

の代わりに[SerializeClass](#serializeclass) `WriteClass`を使用して、クラス参照の読み取りと書き込みの両方を処理できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

## <a name="carchivewriteobject"></a><a name="writeobject"></a>アーカイブ::オブジェクトの書き込み

指定した`CObject`アーカイブを格納します。

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>パラメーター

*Pob*<br/>
格納されているオブジェクトへの定数ポインター。

### <a name="remarks"></a>解説

この関数は通常、挿入 ( `CArchive` **<<**) 演算子が に`CObject`対してオーバーロードすることによって呼び出されます。 `WriteObject`を呼び出すと、`Serialize`アーカイブされたクラスの関数が呼び出されます。

アーカイブを有効にするには、IMPLEMENT_SERIAL マクロを使用する必要があります。 `WriteObject`ASCII クラス名をアーカイブに書き込みます。 このクラス名は、ロード処理中に後で検証されます。 特殊なコード化スキームは、クラスの複数のオブジェクトに対するクラス名の不要な重複を防ぎます。 この方式では、複数のポインターのターゲットであるオブジェクトの冗長ストレージも防止します。

正確なオブジェクト エンコーディング メソッド (ASCII クラス名の存在を含む) は実装の詳細であり、ライブラリの将来のバージョンで変更される可能性があります。

> [!NOTE]
> すべてのオブジェクトの作成、削除、および更新を完了してから、アーカイブを開始します。 アーカイブとオブジェクトの変更を混在させると、アーカイブが破損します。

### <a name="example"></a>例

クラス`CAge`の定義については、[例](../../mfc/reference/coblist-class.md#coblist)を参照してください。

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

## <a name="carchivewritestring"></a><a name="writestring"></a>アーカイブ::書き込み文字列

このメンバー関数を使用して、バッファーからオブジェクトに関連付けられたファイルに`CArchive`データを書き込みます。

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
null で終わるテキスト文字列を含むバッファーへのポインターを指定します。

### <a name="remarks"></a>解説

終端の NULL 文字 ('\0') はファイルに書き込まれません。また、改行は自動的に書き込まれません。

`WriteString`ディスク満杯条件を含むいくつかの条件に応答して例外をスローします。

`Write`また、NULL 文字で終了するのではなく、要求されたバイト数をファイルに書き込みます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[CSocket クラス](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
