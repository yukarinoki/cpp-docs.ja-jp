---
title: CObject クラス
ms.date: 11/04/2016
f1_keywords:
- CObject
- AFX/CObject
- AFX/CObject::CObject
- AFX/CObject::AssertValid
- AFX/CObject::Dump
- AFX/CObject::GetRuntimeClass
- AFX/CObject::IsKindOf
- AFX/CObject::IsSerializable
- AFX/CObject::Serialize
helpviewer_keywords:
- CObject [MFC], CObject
- CObject [MFC], AssertValid
- CObject [MFC], Dump
- CObject [MFC], GetRuntimeClass
- CObject [MFC], IsKindOf
- CObject [MFC], IsSerializable
- CObject [MFC], Serialize
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
ms.openlocfilehash: 515c4e90ee6ab77a6c7c1ae108393ea1aafb7c17
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855318"
---
# <a name="cobject-class"></a>CObject クラス

MFC ライブラリの重要な基底クラスです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|Name|Description|
|----------|-----------------|
|[CObject:: CObject](#cobject)|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CObject:: AssertValid](#assertvalid)|このオブジェクトの整合性を検証します。|
|[CObject::D ump](#dump)|このオブジェクトの診断ダンプを生成します。|
|[CObject:: GetRuntimeClass](#getruntimeclass)|このオブジェクトのクラスに対応する `CRuntimeClass` 構造体を返します。|
|[CObject:: IsKindOf](#iskindof)|このオブジェクトと特定のクラスとの関係をテストします。|
|[CObject:: IsSerializable](#isserializable)|このオブジェクトをシリアル化できるかどうかをテストします。|
|[CObject:: Serialize](#serialize)|アーカイブからのオブジェクトの読み込みまたは保存を行います。|

### <a name="public-operators"></a>パブリック演算子

|Name|Description|
|----------|-----------------|
|[CObject:: operator delete](#operator_delete)|特別な**delete**演算子です。|
|[CObject:: operator new](#operator_new)|特別な**新しい**演算子。|

## <a name="remarks"></a>解説

`CFile` や `CObList`などのライブラリクラスだけでなく、記述するクラスのルートとしても機能します。 `CObject` には、

- シリアル化のサポート

- ランタイムクラス情報

- オブジェクトの診断出力

- コレクションクラスとの互換性

`CObject` は複数の継承をサポートしていないことに注意してください。 派生クラスは、1つの `CObject` 基底クラスのみを持つことができ、`CObject` は階層内の最上位にある必要があります。 ただし、構造体と非 `CObject`派生クラスを右側の複数継承分岐に含めることは許可されています。

クラスの実装と宣言で省略可能なマクロの一部を使用する場合、`CObject` 派生によって大きなメリットが得られます。

第1レベルのマクロ、 [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)および[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)では、階層内のクラス名とその位置への実行時アクセスが許可されます。 これにより、意味のある診断ダンプを行うことができます。

第2レベルのマクロである[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)には、第1レベルのマクロのすべての機能が含まれています。また、"archive" との間でオブジェクトを "シリアル化" できるようにします。

Microsoft Foundation クラスおよびC++クラスの一般的な派生と `CObject`の使用の詳細については、「CObject と[シリアル化](../../mfc/serialization-in-mfc.md)の[使用](../../mfc/using-cobject.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

##  <a name="assertvalid"></a>CObject:: AssertValid

このオブジェクトの整合性を検証します。

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>解説

`AssertValid` は、内部状態を確認することによって、このオブジェクトの有効性チェックを実行します。 ライブラリのデバッグバージョンでは、`AssertValid` によってアサートされ、アサーションが失敗した行番号とファイル名を示すメッセージが表示されてプログラムが終了する場合があります。

独自のクラスを記述する場合は、`AssertValid` 関数をオーバーライドして、自分やクラスの他のユーザーのために診断サービスを提供する必要があります。 通常、オーバーライドされた `AssertValid` は、派生クラスに固有のデータメンバーをチェックする前に、基本クラスの `AssertValid` 関数を呼び出します。

`AssertValid` は**const**関数なので、テスト中にオブジェクトの状態を変更することは許可されません。 独自の派生クラス `AssertValid` 関数は、例外をスローするのではなく、無効なオブジェクトデータを検出するかどうかをアサートする必要があります。

"有効性" の定義は、オブジェクトのクラスによって異なります。 ルールとして、関数は "浅いチェック" を実行する必要があります。 つまり、オブジェクトに他のオブジェクトへのポインターが含まれている場合は、ポインターが null でないかどうかを確認する必要がありますが、ポインターによって参照されるオブジェクトに対して有効性テストを実行する必要はありません。

### <a name="example"></a>例

すべての `CObject` 例で使用される `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

別の例については、「 [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects)」を参照してください。

##  <a name="cobject"></a>CObject:: CObject

これらの関数は、標準の `CObject` コンストラクターです。

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>パラメーター

*objectSrc*<br/>
別の `CObject` への参照

### <a name="remarks"></a>解説

既定のバージョンは、派生クラスのコンストラクターによって自動的に呼び出されます。

クラスがシリアル化可能な場合 (IMPLEMENT_SERIAL マクロが組み込まれている場合)、クラス宣言に既定のコンス トラクター (引数なしのコンス トラクター) が必要です。 既定のコンス トラクターが必要ない場合、private を宣言または「空」のコンス トラクターを宣言します。 詳細については、「 [CObject の使用](../../mfc/using-cobject.md)」を参照してください。

標準C++の既定のクラスコピーコンストラクターは、メンバーごとのコピーを行います。 プライベート `CObject` コピーコンストラクターが存在することは、クラスのコピーコンストラクターが必要であるが使用できない場合に、コンパイラエラーメッセージを保証します。 したがって、クラスにこの機能が必要な場合は、コピーコンストラクターを指定する必要があります。

### <a name="example"></a>例

`CObject` の例で使用されている `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

##  <a name="dump"></a>CObject::D ump

オブジェクトの内容を[CDumpContext](../../mfc/reference/cdumpcontext-class.md)オブジェクトにダンプします。

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
ダンプの診断ダンプコンテキスト (通常は `afxDump`)。

### <a name="remarks"></a>解説

独自のクラスを記述する場合は、`Dump` 関数をオーバーライドして、自分やクラスの他のユーザーのために診断サービスを提供する必要があります。 通常、オーバーライドされた `Dump` は、派生クラスに固有のデータメンバーを出力する前に、基本クラスの `Dump` 関数を呼び出します。 クラスで `IMPLEMENT_DYNAMIC` または IMPLEMENT_SERIAL マクロが使用されている場合、`CObject::Dump` はクラス名を出力します。

> [!NOTE]
>  `Dump` 関数は、出力の最後に改行文字を出力しません。

`Dump` の呼び出しは、Microsoft Foundation Class ライブラリのデバッグバージョンでのみ意味があります。 呼び出し、関数宣言、および関数の実装は、条件付きコンパイルの/ `#endif` ステートメントで **#ifdef _DEBUG**を使用して、かっこで囲む必要があります。

`Dump` は**const**関数であるため、ダンプ中にオブジェクトの状態を変更することはできません。

[CDumpContext 挿入 (< <) 演算子](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt)は、`CObject` ポインターが挿入されたときに `Dump` を呼び出します。

`Dump` は、オブジェクトの "非循環" ダンプのみを許可します。 たとえば、オブジェクトの一覧をダンプできますが、オブジェクトの1つがリスト自体の場合は、最終的にスタックをオーバーフローします。

### <a name="example"></a>例

すべての `CObject` 例で使用される `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

##  <a name="getruntimeclass"></a>CObject:: GetRuntimeClass

このオブジェクトのクラスに対応する `CRuntimeClass` 構造体を返します。

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトのクラスに対応する[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。**NULL**にしないでください。

### <a name="remarks"></a>解説

`CObject`派生クラスごとに1つの `CRuntimeClass` 構造があります。 構造体のメンバーは次のとおりです。

- **LPCSTR m_lpszClassName**ASCII クラス名を格納している null で終わる文字列。

- **int m_nObjectSize**オブジェクトのサイズ (バイト単位)。 オブジェクトに割り当てられたメモリを指すデータメンバーがある場合、そのメモリのサイズは含まれません。

- **UINT m_wSchema**スキーマ番号 (シリアル化クラスの場合は-1)。 スキーマ番号の説明については、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロを参照してください。

- **CObject\* (PASCAL\* m_pfnCreateObject) ()** クラスのオブジェクトを作成する既定のコンストラクターへの関数ポインター (クラスが動的作成をサポートしている場合にのみ有効)。それ以外の場合は**NULL**を返します。

- **CRuntimeClass\* (PASCAL\* m_pfn_GetBaseClass) ()** アプリケーションが AFXDLL バージョンの MFC に動的にリンクされている場合は、基底クラスの `CRuntimeClass` 構造体を返す関数へのポインター。

- **CRuntimeClass\* m_pBaseClass**アプリケーションが MFC に静的にリンクされている場合は、基本クラスの `CRuntimeClass` 構造体へのポインター。

この関数では、クラスの実装で[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)、 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)、または[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロを使用する必要があります。 それ以外の場合は、正しくない結果が返されます。

### <a name="example"></a>例

すべての `CObject` 例で使用される `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

##  <a name="iskindof"></a>CObject:: IsKindOf

このオブジェクトと特定のクラスとの関係をテストします。

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>パラメーター

*pClass*<br/>
`CObject`派生クラスに関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。

### <a name="return-value"></a>戻り値

オブジェクトがクラスに対応している場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、 *pClass*をテストして、(1) これが指定されたクラスのオブジェクトであるか (2)、指定されたクラスから派生したクラスのオブジェクトであるかを確認します。 この関数は、 [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)、 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)、または[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロで宣言されたクラスに対してのみ機能します。

ポリモーフィズム機能をC++損なうため、この関数は広く使用しないでください。 代わりに仮想関数を使用してください。

### <a name="example"></a>例

すべての `CObject` 例で使用される `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

##  <a name="isserializable"></a>CObject:: IsSerializable

このオブジェクトがシリアル化の対象であるかどうかをテストします。

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトをシリアル化できる場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

クラスをシリアル化できるようにするには、その宣言に[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロを含める必要があります。また、実装には[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロが含まれている必要があります。

> [!NOTE]
>  この関数をオーバーライドしないでください。

### <a name="example"></a>例

すべての `CObject` 例で使用される `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

##  <a name="operator_delete"></a>CObject:: operator delete

ライブラリのリリースバージョンでは、operator **delete**は operator **new**によって割り当てられたメモリを解放します。

```
void PASCAL operator delete(void* p);

void PASCAL operator delete(
    void* p,
    void* pPlace);

void PASCAL operator delete(
    void* p,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>解説

デバッグバージョンでは、operator **delete**はメモリリークを検出するように設計された割り当て監視スキームに関与します。

コード行を使用する場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

の実装の前。CPP ファイルを使用すると、3番目のバージョンの**delete**が使用され、後でレポートを作成するために、割り当てられたブロックにファイル名と行番号が格納されます。 追加のパラメーターを指定する必要はありません。マクロがそれを対処します。

デバッグモードで DEBUG_NEW を使用しない場合でも、前に説明したソースファイルの行番号レポートがなくても、リーク検出は発生します。

Operator **new**と**delete**をオーバーライドすると、この診断機能がプランます。

### <a name="example"></a>例

`CObject` の例で使用されている `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

##  <a name="operator_new"></a>CObject:: operator new

ライブラリのリリースバージョンでは、operator **new**は `malloc`と同様の方法で最適なメモリ割り当てを実行します。

```
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>解説

デバッグバージョンでは、operator **new**はメモリリークを検出するように設計された割り当て監視スキームに参加します。

コード行を使用する場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

の実装の前。CPP ファイルを使用すると、**新しい**の2番目のバージョンが使用され、後でレポートを作成するために、割り当てられたブロックにファイル名と行番号が格納されます。 追加のパラメーターを指定する必要はありません。マクロがそれを対処します。

デバッグモードで DEBUG_NEW を使用しない場合でも、前に説明したソースファイルの行番号レポートがなくても、リーク検出は発生します。

> [!NOTE]
>  この演算子をオーバーライドする場合は、 **delete**もオーバーライドする必要があります。 標準ライブラリ `_new_handler` 関数は使用しないでください。

### <a name="example"></a>例

`CObject` の例で使用されている `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

##  <a name="serialize"></a>CObject:: Serialize

アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*金*<br/>
シリアル化またはシリアル化を行う `CArchive` オブジェクト。

### <a name="remarks"></a>解説

シリアル化する各クラスの `Serialize` をオーバーライドする必要があります。 オーバーライドされた `Serialize` は、まず基本クラスの `Serialize` 関数を呼び出す必要があります。

また、クラス宣言で[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロを使用する必要があります。また、実装では、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロを使用する必要があります。

[Carchive:: IsLoading](../../mfc/reference/carchive-class.md#isloading)または[Carchive:: isloading](../../mfc/reference/carchive-class.md#isstoring)を使用して、アーカイブが読み込み中であるか格納されているかを判断します。

`Serialize` は、 [carchive:: ReadObject](../../mfc/reference/carchive-class.md#readobject)および[Carchive:: WriteObject](../../mfc/reference/carchive-class.md#writeobject)によって呼び出されます。 これらの関数は、`CArchive` 挿入演算子 ( **<\<** ) と抽出演算子 ( **>>** ) に関連付けられています。

シリアル化の例については、「[シリアル化: オブジェクト](../../mfc/serialization-serializing-an-object.md)のシリアル化」を参照してください。

### <a name="example"></a>例

すべての `CObject` 例で使用される `CAge` クラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください。

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)
