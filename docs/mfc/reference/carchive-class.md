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
ms.openlocfilehash: 3cf5c3b7a79e846928b5a7ee0af12a3324e141a3
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424627"
---
# <a name="carchive-class"></a>CArchive クラス

を使用すると、オブジェクトの複雑なネットワークを永続的なバイナリ形式 (通常はディスクストレージ) に保存し、それらのオブジェクトが削除された後も保持できます。

## <a name="syntax"></a>構文

```
class CArchive
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CArchive:: CArchive](#carchive)|`CArchive` オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CArchive:: Abort](#abort)|例外をスローせずにアーカイブを閉じます。|
|[CArchive:: Close](#close)|書き込まれていないデータをフラッシュし、`CFile`から切断します。|
|[CArchive:: Flush](#flush)|アーカイブバッファーから書き込まれていないデータをフラッシュします。|
|[CArchive:: GetFile](#getfile)|このアーカイブの `CFile` オブジェクトポインターを取得します。|
|[CArchive:: GetObjectSchema](#getobjectschema)|逆シリアル化されているオブジェクトのバージョンを判断するために、`Serialize` 関数から呼び出されます。|
|[CArchive:: IsBufferEmpty](#isbufferempty)|Windows ソケットの受信プロセス中にバッファーが空になっているかどうかを判断します。|
|[CArchive:: IsLoading](#isloading)|アーカイブが読み込み中かどうかを判断します。|
|[CArchive:: IsStoring](#isstoring)|アーカイブが格納されているかどうかを判断します。|
|[CArchive:: MapObject](#mapobject)|ファイルにシリアル化されていないが、サブオブジェクトで参照できるオブジェクトをマップに配置します。|
|[CArchive:: Read](#read)|生バイトを読み取ります。|
|[CArchive:: ReadClass](#readclass)|以前に `WriteClass`で格納されたクラス参照を読み取ります。|
|[CArchive:: ReadObject](#readobject)|オブジェクトの `Serialize` 関数を呼び出して読み込みます。|
|[CArchive:: ReadString](#readstring)|1行のテキストを読み取ります。|
|[CArchive:: SerializeClass](#serializeclass)|`CArchive`の方向に応じて、`CArchive` オブジェクトへのクラス参照を読み取りまたは書き込みます。|
|[CArchive:: SetLoadParams](#setloadparams)|読み込み配列のサイズを設定します。 オブジェクトが読み込まれる前、または `MapObject` または `ReadObject` が呼び出される前に、を呼び出す必要があります。|
|[CArchive:: SetObjectSchema](#setobjectschema)|Archive オブジェクトに格納されているオブジェクトスキーマを設定します。|
|[CArchive:: SetStoreParams](#setstoreparams)|シリアル化プロセス中に一意のオブジェクトを識別するために使用されるマップのハッシュテーブルのサイズとブロックサイズを設定します。|
|[CArchive:: Write](#write)|生のバイトを書き込みます。|
|[CArchive:: WriteClass](#writeclass)|`CRuntimeClass` への参照を `CArchive`に書き込みます。|
|[CArchive:: WriteObject](#writeobject)|オブジェクトの `Serialize` 関数を呼び出して格納します。|
|[CArchive:: WriteString](#writestring)|1行のテキストを書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|Name|Description|
|----------|-----------------|
|[CArchive:: operator &lt;&lt;](#operator_lt_lt)|オブジェクトとプリミティブ型をアーカイブに格納します。|
|[CArchive:: operator &gt;&gt;](#operator_gt_gt)|アーカイブからオブジェクトとプリミティブ型を読み込みます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|Description|
|----------|-----------------|
|[CArchive:: m_pDocument](#m_pdocument)||

## <a name="remarks"></a>解説

`CArchive` には基底クラスがありません。

後で永続ストレージからオブジェクトを読み込み、メモリに再作成することができます。 データを永続化するこのプロセスは、"シリアル化" と呼ばれます。

アーカイブオブジェクトは、バイナリストリームの一種と考えることができます。 入力/出力ストリームと同様に、アーカイブはファイルに関連付けられ、バッファーによるデータの書き込みとストレージからのデータの読み取りを許可します。 入力/出力ストリームは ASCII 文字のシーケンスを処理しますが、アーカイブでは、バイナリオブジェクトデータを効率的かつ冗長な形式で処理します。

`CArchive` オブジェクトを作成する前に、 [CFile](../../mfc/reference/cfile-class.md)オブジェクトを作成する必要があります。 また、アーカイブの読み込み/格納状態が、ファイルのオープンモードと互換性があることを確認する必要があります。 ファイルごとにアクティブなアーカイブは1つに制限されています。

`CArchive` オブジェクトを構築する場合は、開いているファイルを表すクラス `CFile` (または派生クラス) のオブジェクトにアタッチします。 また、アーカイブを読み込みまたは保存に使用するかどうかも指定します。 `CArchive` オブジェクトは、プリミティブ型だけでなく、シリアル化用にデザインされた[CObject](../../mfc/reference/cobject-class.md)派生クラスのオブジェクトも処理できます。 シリアル化可能なクラスには、通常、`Serialize` のメンバー関数があります。また、「クラス `CObject`」で説明されているように、通常は[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを使用します。

オーバーロードされた抽出 ( **>>** ) および挿入 ( **<<** ) 演算子は、プリミティブ型と `CObject`派生クラスの両方をサポートする便利なアーカイブプログラミングインターフェイスです。

`CArchive` は、MFC の Windows ソケットクラス[CSocket](../../mfc/reference/csocket-class.md)と[CSocketFile](../../mfc/reference/csocketfile-class.md)を使用したプログラミングもサポートしています。 [Isbufferempty](#isbufferempty)メンバー関数は、その使用法をサポートしています。

`CArchive`の詳細については、「[シリアル化](../../mfc/serialization-in-mfc.md)と[Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CArchive`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

##  <a name="abort"></a>CArchive:: Abort

例外をスローせずにアーカイブを閉じるには、この関数を呼び出します。

```
void Abort ();
```

### <a name="remarks"></a>解説

`CArchive` デストラクターは通常、`Close`を呼び出します。これにより、関連付けられた `CFile` オブジェクトに保存されていないすべてのデータがフラッシュされます。 これにより、例外が発生する可能性があります。

これらの例外をキャッチする場合は `Abort`を使用することをお勧めします。これにより、`CArchive` オブジェクトによって例外が発生することはありません。 例外を処理する場合、`CArchive::Abort` は、 [CArchive:: `Abort` Close](#close)とは異なり、エラーを無視するため、エラー発生時に例外をスローしません。

**New**を使用してヒープに `CArchive` オブジェクトを割り当てる場合は、ファイルを閉じた後でそのオブジェクトを削除する必要があります。

### <a name="example"></a>例

  [CArchive:: WriteClass](#writeclass)の例を参照してください。

##  <a name="carchive"></a>CArchive:: CArchive

`CArchive` オブジェクトを構築し、オブジェクトの読み込みまたは格納に使用するかどうかを指定します。

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>パラメーター

*pFile*<br/>
永続データの最終的な変換元または転送先である `CFile` オブジェクトへのポインター。

*Evaluationmode*<br/>
オブジェクトがアーカイブから読み込まれるか、アーカイブに格納されるかを指定するフラグ。 *Nmode*パラメーターには、次のいずれかの値を指定する必要があります。

- `CArchive::load` は、アーカイブからデータを読み込みます。 `CFile` 読み取りアクセス許可のみが必要です。

- `CArchive::store` は、データをアーカイブに保存します。 `CFile` 書き込みアクセス許可が必要です。

- `CArchive::bNoFlushOnDelete` は、アーカイブデストラクターが呼び出されたときに、アーカイブが自動的に `Flush` を呼び出さないようにします。 このフラグを設定した場合は、デストラクターが呼び出される前に `Close` を明示的に呼び出す必要があります。 そうしないと、データが破損します。

*nBufSize*<br/>
内部ファイルバッファーのサイズをバイト単位で指定する整数です。 既定のバッファーサイズは4096バイトであることに注意してください。 大量のオブジェクトを定期的にアーカイブする場合は、ファイルバッファーサイズの倍数である大きなバッファーサイズを使用すると、パフォーマンスが向上します。

*lpBuf*<br/>
ユーザーが指定し*たサイズの*バッファーへのポインターです (省略可能)。 このパラメーターを指定しない場合、アーカイブによってローカルヒープからバッファーが割り当てられ、オブジェクトが破棄されると解放されます。 アーカイブでは、ユーザーが指定したバッファーは解放されません。

### <a name="remarks"></a>解説

アーカイブを作成した後で、この仕様を変更することはできません。

アーカイブを閉じるまで、`CFile` 操作を使用してファイルの状態を変更することはできません。 このような操作を行うと、アーカイブの整合性が損なわれます。 シリアル化中にファイルポインターの位置にアクセスするには、アーカイブのファイルオブジェクトを[GetFile](#getfile)メンバー関数から取得してから、 [CFile:: GetPosition](../../mfc/reference/cfile-class.md#getposition)関数を使用します。 ファイルポインターの位置を取得する前に、 [CArchive:: Flush](#flush)を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

##  <a name="close"></a>CArchive:: Close

バッファーに残っているすべてのデータをフラッシュし、アーカイブを閉じ、ファイルからアーカイブを切断します。

```
void Close();
```

### <a name="remarks"></a>解説

アーカイブに対するそれ以上の操作は許可されていません。 アーカイブを閉じた後、同じファイルに対して別のアーカイブを作成するか、ファイルを閉じることができます。

このメンバー関数は、すべてのデータがアーカイブからファイルに転送されることを保証し、アーカイブを使用できないように `Close` します。 ファイルからストレージメディアへの転送を完了するには、最初に[CFile:: Close](../../mfc/reference/cfile-class.md#close)を使用してから、`CFile` オブジェクトを破棄する必要があります。

### <a name="example"></a>例

  [CArchive:: WriteString](#writestring)の例を参照してください。

##  <a name="flush"></a>CArchive:: Flush

アーカイブバッファー内の残りのデータを強制的にファイルに書き込みます。

```
void Flush();
```

### <a name="remarks"></a>解説

メンバー関数 `Flush` は、すべてのデータがアーカイブからファイルに転送されるようにします。 ファイルからストレージメディアへの転送を完了するには、 [CFile:: Close](../../mfc/reference/cfile-class.md#close)を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

##  <a name="getfile"></a>CArchive:: GetFile

このアーカイブの `CFile` オブジェクトポインターを取得します。

```
CFile* GetFile() const;
```

### <a name="return-value"></a>戻り値

使用されている `CFile` オブジェクトへの定数ポインター。

### <a name="remarks"></a>解説

`GetFile`を使用する前に、アーカイブをフラッシュする必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

##  <a name="getobjectschema"></a>CArchive:: GetObjectSchema

現在逆シリアル化されているオブジェクトのバージョンを確認するには、`Serialize` 関数からこの関数を呼び出します。

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>戻り値

逆シリアル化中に、読み取るオブジェクトのバージョン。

### <a name="remarks"></a>解説

この関数の呼び出しは、`CArchive` オブジェクトが読み込まれている場合にのみ有効です ( [CArchive:: IsLoading](#isloading)は0以外の値を返します)。 `Serialize` 関数の最初の呼び出しである必要があり、1回だけ呼び出されます。 戻り値 (UINT)-1 は、バージョン番号が不明であることを示します。

`CObject`派生クラスでは、(ビットごとの**or**を使用して) スキーマバージョン自体 (IMPLEMENT_SERIAL マクロ) と組み合わせて VERSIONABLE_SCHEMA を使用して、"バージョン管理可能オブジェクト" を作成できます。これは、`Serialize` メンバー関数が複数のバージョンを読み取ることができるオブジェクトです。 既定のフレームワーク機能 (VERSIONABLE_SCHEMA なし) は、バージョンが一致しない場合に例外をスローすることです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

##  <a name="isbufferempty"></a>CArchive:: IsBufferEmpty

このメンバー関数を呼び出して、archive オブジェクトの内部バッファーが空であるかどうかを確認します。

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>戻り値

アーカイブのバッファーが空の場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、MFC Windows Sockets クラス `CSocketFile`を使用したプログラミングをサポートするために用意されています。 `CFile` オブジェクトに関連付けられたアーカイブには、このファイルを使用する必要はありません。

`CSocketFile` オブジェクトに関連付けられたアーカイブで `IsBufferEmpty` を使用する理由は、アーカイブのバッファーに複数のメッセージまたはレコードが含まれている可能性があるためです。 1つのメッセージを受信した後、`IsBufferEmpty` を使用して、バッファーが空になるまでデータの受信を継続するループを制御する必要があります。 詳細については、「`CAsyncSocket`クラスの[Receive](../../mfc/reference/casyncsocket-class.md#receive)メンバー関数」を参照してください。 `IsBufferEmpty`の使用方法を示しています。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

##  <a name="isloading"></a>CArchive:: IsLoading

アーカイブがデータを読み込んでいるかどうかを判断します。

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>戻り値

アーカイブが現在読み込みに使用されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、アーカイブされたクラスの `Serialize` 関数によって呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

##  <a name="isstoring"></a>CArchive:: IsStoring

アーカイブがデータを格納しているかどうかを判断します。

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>戻り値

アーカイブが現在使用されている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、アーカイブされたクラスの `Serialize` 関数によって呼び出されます。

アーカイブの `IsStoring` ステータスが0以外の場合、`IsLoading` ステータスは0になり、その逆も同様になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

##  <a name="mapobject"></a>CArchive:: MapObject

このメンバー関数を呼び出して、実際にはファイルにシリアル化されていないが、サブオブジェクトで参照できるオブジェクトをマップに配置します。

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>パラメーター

*pOb*<br/>
格納されているオブジェクトへの定数ポインター。

### <a name="remarks"></a>解説

たとえば、ドキュメントをシリアル化することはできませんが、ドキュメントに含まれる項目をシリアル化することになります。 `MapObject`を呼び出すことにより、これらの項目 (サブオブジェクト) がドキュメントを参照できるようになります。 また、シリアル化されたサブ項目は*m_pDocument*バックポインターをシリアル化できます。

`CArchive` オブジェクトに格納して読み込むときに、`MapObject` を呼び出すことができます。 `MapObject` は、シリアル化と逆シリアル化の間に `CArchive` オブジェクトによって保持される内部データ構造に指定されたオブジェクトを追加しますが、 [ReadObject](#readobject)と[WriteObject](#writeobject)とは異なり、オブジェクトで serialize を呼び出しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

##  <a name="m_pdocument"></a>CArchive:: m_pDocument

NULL に設定すると、既定では、`CDocument` へのポインターは、`CArchive` インスタンスのユーザーが必要とする任意のものに設定できます。

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>解説

このポインターの一般的な使用方法は、シリアル化プロセスに関する追加情報をシリアル化するすべてのオブジェクトに伝達することです。 これは、ドキュメント内のオブジェクトが必要に応じてドキュメントにアクセスできるように、シリアル化されているドキュメント (`CDocument`派生クラス) を使用してポインターを初期化することで実現されます。 このポインターは、シリアル化中に `COleClientItem` オブジェクトによっても使用されます。

フレームワークは、ユーザーが File Open または Save コマンドを発行したときに、シリアル化されるドキュメントに*m_pDocument*を設定します。 オブジェクトのリンクと埋め込み (OLE) コンテナードキュメントを、File Open または Save 以外の理由でシリアル化する場合は、 *m_pDocument*を明示的に設定する必要があります。 たとえば、コンテナードキュメントをクリップボードにシリアル化するときに、この操作を行います。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

##  <a name="operator_lt_lt"></a>CArchive:: operator &lt;&lt;

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

1行に複数の挿入演算子を使用できるようにする `CArchive` 参照。

### <a name="remarks"></a>解説

上記の最後の2つのバージョンは、64ビットの整数を格納するためのものです。

クラスの実装で IMPLEMENT_SERIAL マクロを使用した場合、`CObject` に対してオーバーロードされた挿入演算子は、保護された `WriteObject`を呼び出します。 次に、この関数はクラスの `Serialize` 関数を呼び出します。

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)挿入演算子 (< <) は、診断ダンプをサポートし、アーカイブに保存します。

### <a name="example"></a>例

この例では、 **int**型と**long**型を使用して < < `CArchive` 挿入演算子を使用する方法を示します。

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>例

この例2では、`CStringT` 型を使用して < < `CArchive` 挿入演算子を使用する方法を示します。

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

##  <a name="operator_gt_gt"></a>CArchive:: operator &gt;&gt;

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

複数の抽出演算子を1行に対して有効にする `CArchive` 参照。

### <a name="remarks"></a>解説

上記の最後の2つのバージョンは、64ビットの整数を読み込むためのものです。

クラスの実装で IMPLEMENT_SERIAL マクロを使用した場合、`CObject` に対してオーバーロードされた抽出演算子は、プロテクト `ReadObject` 関数 (0 以外のランタイムクラスポインター) を呼び出します。 次に、この関数はクラスの `Serialize` 関数を呼び出します。

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)抽出演算子 (> >) では、アーカイブからの読み込みがサポートされています。

### <a name="example"></a>例

この例では、 **int**型の > > `CArchive` 抽出演算子の使用方法を示します。

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>例

この例では、> 型を使用して\< および > `CStringT` < `CArchive` の挿入および抽出演算子の使用方法を示します。

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

##  <a name="read"></a>CArchive:: Read

アーカイブから指定されたバイト数を読み取ります。

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
アーカイブから読み取ったデータを受信するユーザー指定のバッファーへのポインター。

*N1 日*<br/>
アーカイブから読み取るバイト数を指定する符号なし整数。

### <a name="return-value"></a>戻り値

実際に読み取られたバイト数を格納している符号なし整数。 戻り値が要求された数より小さい場合は、ファイルの末尾に達しています。 ファイルの終わりの条件では、例外はスローされません。

### <a name="remarks"></a>解説

アーカイブでは、バイトは解釈されません。

`Serialize` 関数内で `Read` メンバー関数を使用すると、オブジェクトに格納されている通常の構造体を読み取ることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

##  <a name="readclass"></a>CArchive:: ReadClass

このメンバー関数を呼び出して、以前に[Writeclass](#writeclass)で格納したクラスへの参照を読み取ります。

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>パラメーター

*pClassRefRequested*<br/>
要求されたクラス参照に対応する[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。 NULL にすることができます。

*pSchema*<br/>
以前に格納されていたランタイムクラスのスキーマへのポインター。

*pObTag*<br/>
オブジェクトの一意のタグを参照する数値。 [ReadObject](#readobject)の実装によって内部的に使用されます。 高度なプログラミングのためだけに公開されています。*Pobtag*は通常 NULL にする必要があります。

### <a name="return-value"></a>戻り値

[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。

### <a name="remarks"></a>解説

要求された*Pclassrefrequested* NULL でない場合、`ReadClass` は、アーカイブされたクラス情報がランタイムクラスと互換性があるかどうかを確認します。 互換性がない場合、`ReadClass` は[Cアーカイブ例外](../../mfc/reference/carchiveexception-class.md)をスローします。

ランタイムクラスは[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)を使用する必要があります。それ以外の場合、`ReadClass` は[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)をスローします。

*Pschema*が NULL の場合、格納されているクラスのスキーマは、 [CArchive:: getobjectschema](#getobjectschema); を呼び出すことによって取得できます。それ以外の場合、 <strong>\*</strong> *pschema*には、以前に格納されていたランタイムクラスのスキーマが格納されます。

クラス参照の読み取りと書き込みの両方を処理する `ReadClass`ではなく、 [SerializeClass](#serializeclass)を使用できます。

### <a name="example"></a>例

  [CArchive:: WriteClass](#writeclass)の例を参照してください。

##  <a name="readobject"></a>CArchive:: ReadObject

アーカイブからオブジェクトデータを読み取り、適切な型のオブジェクトを構築します。

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>パラメーター

*pClass*<br/>
読み取ることが想定されているオブジェクトに対応する[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体への定数ポインター。

### <a name="return-value"></a>戻り値

Cobject [:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)を使用して、正しい派生クラスに安全にキャストする必要がある[cobject](../../mfc/reference/cobject-class.md)ポインター。

### <a name="remarks"></a>解説

通常、この関数は、 [CObject](../../mfc/reference/cobject-class.md)ポインターに対してオーバーロードされた `CArchive` 抽出 ( **>>** ) 演算子によって呼び出されます。 `ReadObject`は、アーカイブされたクラスの `Serialize` 関数を呼び出します。

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロによって取得される0以外の*pClass*パラメーターを指定すると、関数はアーカイブされたオブジェクトのランタイムクラスを検証します。 これは、クラスの実装で IMPLEMENT_SERIAL マクロを使用したことを前提としています。

### <a name="example"></a>例

  [CArchive:: WriteObject](#writeobject)の例を参照してください。

##  <a name="readstring"></a>CArchive:: ReadString

このメンバー関数を呼び出して、`CArchive` オブジェクトに関連付けられたファイルからテキストデータをバッファーに読み込みます。

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>パラメーター

*rString*<br/>
CArchive オブジェクトに関連付けられたファイルから読み取られた後に、結果の文字列が格納される[CString](../../atl-mfc-shared/reference/cstringt-class.md)への参照。

*lpsz*<br/>
Null で終わるテキスト文字列を受け取るユーザー指定のバッファーへのポインターを指定します。

*N1 日*<br/>
読み取る最大文字数を指定します。 は、 *lpsz*バッファーのサイズより1小さい値にする必要があります。

### <a name="return-value"></a>戻り値

BOOL を返すバージョンでは、成功した場合は TRUE になります。それ以外の場合は FALSE。

`LPTSTR`を返すバージョンでは、テキストデータを格納しているバッファーへのポインター。ファイルの終わりに達した場合は NULL です。

### <a name="remarks"></a>解説

*N1 日*パラメーターが指定されたメンバー関数のバージョンでは、バッファーは*n1 日*文字の上限まで保持します。 読み取りは、復帰とラインフィードのペアによって停止されます。 末尾の改行文字は常に削除されます。 どちらの場合も、null 文字 (' \ 0 ') が追加されます。

[CArchive:: Read](#read)は、テキストモード入力でも使用できますが、復帰とラインフィードのペアで終了することはありません。

### <a name="example"></a>例

  [CArchive:: WriteString](#writestring)の例を参照してください。

##  <a name="serializeclass"></a>CArchive:: SerializeClass

基底クラスのバージョン情報を格納して読み込む場合は、このメンバー関数を呼び出します。

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>パラメーター

*pClassRef*<br/>
基底クラスのランタイムクラスオブジェクトへのポインター。

### <a name="remarks"></a>解説

`SerializeClass` は、`CArchive`の方向に応じて、クラスへの参照を `CArchive` オブジェクトに対して読み取りまたは書き込みを行います。 基底クラスのオブジェクトをシリアル化する便利な方法として、 [Readclass](#readclass)と[writeclass](#writeclass)の代わりに `SerializeClass` を使用します。`SerializeClass` に必要なコードが少なく、パラメーターが少なくなっています。

`ReadClass`と同様に、`SerializeClass` アーカイブされたクラス情報がランタイムクラスと互換性があるかどうかを確認します。 互換性がない場合、`SerializeClass` は[Cアーカイブ例外](../../mfc/reference/carchiveexception-class.md)をスローします。

ランタイムクラスは[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)を使用する必要があります。それ以外の場合、`SerializeClass` は[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)をスローします。

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class)マクロを使用して、 *pRuntimeClass*パラメーターの値を取得します。 基本クラスでは、 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを使用する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

##  <a name="setloadparams"></a>CArchive:: SetLoadParams

アーカイブから多数の `CObject`派生オブジェクトを読み取る場合は、`SetLoadParams` を呼び出します。

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>パラメーター

*nGrowBy*<br/>
サイズの増加が必要な場合に割り当てる要素スロットの最小数。

### <a name="remarks"></a>解説

`CArchive` は、load 配列を使用して、アーカイブに格納されているオブジェクトへの参照を解決します。 `SetLoadParams` を使用すると、読み込み配列のサイズを大きくすることができます。

オブジェクトが読み込まれた後、または[Mapobject](#mapobject)または[ReadObject](#readobject)が呼び出された後に `SetLoadParams` を呼び出すことはできません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="setobjectschema"></a>CArchive:: SetObjectSchema

Archive オブジェクトに格納されているオブジェクトスキーマを*Nschema*に設定するには、このメンバー関数を呼び出します。

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>パラメーター

*nSchema*<br/>
オブジェクトのスキーマを指定します。

### <a name="remarks"></a>解説

次に[Getobjectschema](#getobjectschema)を呼び出すと、 *nschema*に格納されている値が返されます。

高度なバージョン管理には `SetObjectSchema` を使用します。たとえば、派生クラスの `Serialize` 関数で特定のバージョンを強制的に読み取る場合などです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

##  <a name="setstoreparams"></a>CArchive:: SetStoreParams

多数の `CObject`派生オブジェクトをアーカイブに格納する場合は、`SetStoreParams` を使用します。

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>パラメーター

*nHashSize*<br/>
インターフェイスポインターマップのハッシュテーブルのサイズ。 は素数である必要があります。

*nBlockSize*<br/>
パラメーターを拡張するためのメモリ割り当ての粒度を指定します。 最高のパフォーマンスを得るには、2の累乗である必要があります。

### <a name="remarks"></a>解説

`SetStoreParams` では、シリアル化プロセス中に一意のオブジェクトを識別するために使用されるマップのハッシュテーブルサイズとブロックサイズを設定できます。

オブジェクトが格納された後、または[Mapobject](#mapobject)または[WriteObject](#writeobject)が呼び出された後に `SetStoreParams` を呼び出すことはできません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="write"></a>CArchive:: Write

指定されたバイト数をアーカイブに書き込みます。

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>パラメーター

*lpBuf*<br/>
アーカイブに書き込まれるデータを格納する、ユーザーが指定したバッファーへのポインター。

*N1 日*<br/>
アーカイブに書き込むバイト数を指定する整数。

### <a name="remarks"></a>解説

アーカイブでは、バイトはフォーマットされません。

`Serialize` 関数内で `Write` メンバー関数を使用すると、オブジェクトに格納されている通常の構造体を書き込むことができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

##  <a name="writeclass"></a>CArchive:: WriteClass

派生クラスのシリアル化時に、基本クラスのバージョンおよびクラス情報を格納するには、`WriteClass` を使用します。

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>パラメーター

*pClassRef*<br/>
要求されたクラス参照に対応する[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。

### <a name="remarks"></a>解説

`WriteClass` は、基本クラスの[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)への参照を `CArchive`に書き込みます。 参照を取得するには、 [CArchive:: ReadClass](#readclass)を使用します。

`WriteClass` は、アーカイブされたクラス情報がランタイムクラスと互換性があるかどうかを確認します。 互換性がない場合、`WriteClass` は[Cアーカイブ例外](../../mfc/reference/carchiveexception-class.md)をスローします。

ランタイムクラスは[DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)を使用する必要があります。それ以外の場合、`WriteClass` は[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)をスローします。

クラス参照の読み取りと書き込みの両方を処理する `WriteClass`ではなく、 [SerializeClass](#serializeclass)を使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

##  <a name="writeobject"></a>CArchive:: WriteObject

指定された `CObject` をアーカイブに格納します。

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>パラメーター

*pOb*<br/>
格納されているオブジェクトへの定数ポインター。

### <a name="remarks"></a>解説

通常、この関数は `CObject`に対してオーバーロードされた `CArchive` 挿入 ( **<<** ) 演算子によって呼び出されます。 `WriteObject`は、アーカイブされたクラスの `Serialize` 関数を呼び出します。

IMPLEMENT_SERIAL マクロを使用してアーカイブを有効にする必要があります。 `WriteObject` は、ASCII クラス名をアーカイブに書き込みます。 このクラス名は、読み込み処理中に後で検証されます。 特別なエンコード方式を使用すると、クラスの複数のオブジェクトに対して、不要なクラス名の重複を防ぐことができます。 また、このスキームにより、複数のポインターのターゲットであるオブジェクトの冗長ストレージも防止されます。

厳密なオブジェクトエンコードメソッド (ASCII クラス名の有無を含む) は実装の詳細であり、ライブラリの将来のバージョンで変更される可能性があります。

> [!NOTE]
>  アーカイブを開始する前に、すべてのオブジェクトの作成、削除、および更新を完了します。 アーカイブとオブジェクトの変更が混在していると、アーカイブが破損します。

### <a name="example"></a>例

クラス `CAge`の定義については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist)」の例を参照してください。

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

##  <a name="writestring"></a>CArchive:: WriteString

このメンバー関数を使用すると、バッファーから `CArchive` オブジェクトに関連付けられたファイルにデータを書き込むことができます。

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
Null で終わるテキスト文字列を格納しているバッファーへのポインターを指定します。

### <a name="remarks"></a>解説

終端の null 文字 (' \ 0 ') はファイルに書き込まれません。また、改行も自動的に書き込まれません。

`WriteString` は、ディスク全体の条件など、いくつかの条件に応じて例外をスローします。

`Write` も使用できますが、null 文字で終了するのではなく、要求されたバイト数をファイルに書き込みます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[CSocket クラス](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile クラス](../../mfc/reference/csocketfile-class.md)
