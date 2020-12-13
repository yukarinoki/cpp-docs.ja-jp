---
description: '詳細: CObject クラス'
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
ms.openlocfilehash: bd093307f159a6d7abe83d9fdd9ad6898a19e4ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331465"
---
# <a name="cobject-class"></a>CObject クラス

MFC ライブラリの重要な基底クラスです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CObject:: CObject](#cobject)|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CObject:: AssertValid](#assertvalid)|このオブジェクトの整合性を検証します。|
|[CObject::D ump](#dump)|このオブジェクトの診断ダンプを生成します。|
|[CObject:: GetRuntimeClass](#getruntimeclass)|`CRuntimeClass`このオブジェクトのクラスに対応する構造体を返します。|
|[CObject:: IsKindOf](#iskindof)|このオブジェクトと特定のクラスとの関係をテストします。|
|[CObject:: IsSerializable](#isserializable)|このオブジェクトをシリアル化できるかどうかをテストします。|
|[CObject:: Serialize](#serialize)|アーカイブからのオブジェクトの読み込みまたは保存を行います。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CObject:: operator delete](#operator_delete)|特別な **`delete`** 演算子。|
|[CObject:: operator new](#operator_new)|特別な **`new`** 演算子。|

## <a name="remarks"></a>解説

これは、やなどのライブラリクラスだけでなく、記述するクラスのルートとしても機能し `CFile` `CObList` ます。 `CObject` 基本的なサービスを提供します。

- シリアル化のサポート

- ランタイムクラス情報

- オブジェクトの診断出力

- コレクションクラスとの互換性

で `CObject` は、複数の継承がサポートされていないことに注意してください。 派生クラスは基底クラスを1つだけ持つことができ、 `CObject` `CObject` 階層の最上位にある必要があります。 ただし、構造と非 `CObject` 派生クラスを右側の複数継承分岐に含めることは許可されています。

`CObject`クラスの実装と宣言で省略可能なマクロの一部を使用すると、派生の大きな利点が得られます。

第1レベルのマクロ、 [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic) および [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)では、階層内のクラス名とその位置への実行時アクセスが許可されます。 これにより、意味のある診断ダンプを行うことができます。

第2レベルのマクロである [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) と [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)には、第1レベルのマクロのすべての機能が含まれています。また、"archive" との間でオブジェクトを "シリアル化" できるようにします。

一般的な、およびを使用した Microsoft Foundation classes と C++ クラスの派生の詳細について `CObject` は、「 [CObject](../../mfc/using-cobject.md) と [シリアル化](../../mfc/serialization-in-mfc.md)の使用」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CObject`

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a> CObject:: AssertValid

このオブジェクトの整合性を検証します。

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>解説

`AssertValid` 内部状態を確認することにより、このオブジェクトの有効性チェックを実行します。 ライブラリのデバッグバージョンでは、に `AssertValid` よってアサートが発生し、アサーションが失敗した行番号とファイル名を示すメッセージが表示されてプログラムが終了する場合があります。

独自のクラスを記述する場合は、関数をオーバーライドして、 `AssertValid` 自分やクラスの他のユーザーに診断サービスを提供する必要があります。 通常、オーバーライドされたは、 `AssertValid` `AssertValid` 派生クラスに固有のデータメンバーをチェックする前に、基本クラスの関数を呼び出します。

は関数であるため `AssertValid` **`const`** 、テスト中にオブジェクトの状態を変更することはできません。 独自の派生クラス関数は、例外をスローするの `AssertValid` ではなく、無効なオブジェクトデータを検出するかどうかをアサートする必要があります。

"有効性" の定義は、オブジェクトのクラスによって異なります。 ルールとして、関数は "浅いチェック" を実行する必要があります。 つまり、オブジェクトに他のオブジェクトへのポインターが含まれている場合は、ポインターが null でないかどうかを確認する必要がありますが、ポインターによって参照されるオブジェクトに対して有効性テストを実行する必要はありません。

### <a name="example"></a>例

すべての例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

別の例については、「 [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects)」を参照してください。

## <a name="cobjectcobject"></a><a name="cobject"></a> CObject:: CObject

これらの関数は、標準 `CObject` コンストラクターです。

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>パラメーター

*objectSrc*<br/>
別のへの参照 `CObject`

### <a name="remarks"></a>解説

既定のバージョンは、派生クラスのコンストラクターによって自動的に呼び出されます。

クラスがシリアル化できる (IMPLEMENT_SERIAL マクロを含む) 場合は、クラス宣言に既定のコンストラクター (引数なしのコンストラクター) が必要です。 既定のコンストラクターが不要な場合は、プライベートまたは保護された "空の" コンストラクターを宣言します。 詳細については、「 [CObject の使用](../../mfc/using-cobject.md)」を参照してください。

標準 C++ の既定のクラスコピーコンストラクターは、メンバーごとのコピーを行います。 プライベートコピーコンストラクターが存在することは、 `CObject` クラスのコピーコンストラクターが必要であるが使用できない場合に、コンパイラエラーメッセージを保証します。 したがって、クラスにこの機能が必要な場合は、コピーコンストラクターを指定する必要があります。

### <a name="example"></a>例

例で使用されているクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a> CObject::D ump

オブジェクトの内容を [CDumpContext](../../mfc/reference/cdumpcontext-class.md) オブジェクトにダンプします。

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
ダンプの診断ダンプコンテキスト (通常は) `afxDump` 。

### <a name="remarks"></a>解説

独自のクラスを記述する場合は、関数をオーバーライドして、 `Dump` 自分やクラスの他のユーザーに診断サービスを提供する必要があります。 通常、オーバーライドされたは、 `Dump` `Dump` 派生クラスに固有のデータメンバーを出力する前に、基本クラスの関数を呼び出します。 `CObject::Dump` クラスでまたは IMPLEMENT_SERIAL マクロを使用している場合は、クラス名を出力し `IMPLEMENT_DYNAMIC` ます。

> [!NOTE]
> `Dump`関数は、出力の末尾に改行文字を出力しません。

`Dump` 呼び出しは、Microsoft Foundation Class ライブラリのデバッグバージョンでのみ意味があります。 呼び出し、関数宣言、および関数の実装は、  /  `#endif` 条件付きコンパイルの #ifdef _DEBUG ステートメントで囲む必要があります。

は関数であるため `Dump` **`const`** 、ダンプ中にオブジェクトの状態を変更することはできません。

[CDumpContext 挿入 (<<) 演算子](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt)は、 `Dump` `CObject` ポインターが挿入されたときにを呼び出します。

`Dump` オブジェクトの "非循環" ダンプのみを許可します。 たとえば、オブジェクトの一覧をダンプできますが、オブジェクトの1つがリスト自体の場合は、最終的にスタックをオーバーフローします。

### <a name="example"></a>例

すべての例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a> CObject:: GetRuntimeClass

`CRuntimeClass`このオブジェクトのクラスに対応する構造体を返します。

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトのクラスに対応する [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 構造体へのポインター。 **NULL** にしないでください。

### <a name="remarks"></a>解説

`CRuntimeClass`各派生クラスには1つの構造体があり `CObject` ます。 構造体のメンバーは次のとおりです。

- **LPCSTR m_lpszClassName** ASCII クラス名を格納している null で終わる文字列。

- **int m_nObjectSize** オブジェクトのサイズ (バイト単位)。 オブジェクトに割り当てられたメモリを指すデータメンバーがある場合、そのメモリのサイズは含まれません。

- **UINT m_wSchema** スキーマ番号 (シリアル化クラスの場合は-1)。 スキーマ番号の説明については、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) マクロを参照してください。

- **CObject \* (PASCAL \* m_pfnCreateObject) ()** クラスのオブジェクトを作成する既定のコンストラクターへの関数ポインター。クラスが動的作成をサポートしている場合にのみ有効です。それ以外の場合は **NULL** を返します。

- **CRuntimeClass \* (PASCAL \* m_pfn_GetBaseClass) ()** アプリケーションが AFXDLL バージョンの MFC に動的にリンクされている場合は、 `CRuntimeClass` 基底クラスの構造を返す関数へのポインター。

- **CRuntimeClass \* m_pBaseClass** 、アプリケーションが MFC に静的にリンクされている場合は、 `CRuntimeClass` 基本クラスの構造体へのポインターです。

この関数では、クラスの実装で [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)、 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)、または [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) マクロを使用する必要があります。 それ以外の場合は、正しくない結果が返されます。

### <a name="example"></a>例

すべての例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a> CObject:: IsKindOf

このオブジェクトと特定のクラスとの関係をテストします。

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>パラメーター

*pClass*<br/>
派生クラスに関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 構造体へのポインター `CObject` 。

### <a name="return-value"></a>戻り値

オブジェクトがクラスに対応している場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、 *pClass* をテストして、(1) これが指定されたクラスのオブジェクトであるか (2)、指定されたクラスから派生したクラスのオブジェクトであるかを確認します。 この関数は、 [DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)、 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)、または [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) マクロで宣言されたクラスに対してのみ機能します。

C++ のポリモーフィズム機能を損なうため、この関数は広く使用しないでください。 代わりに仮想関数を使用してください。

### <a name="example"></a>例

すべての例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a> CObject:: IsSerializable

このオブジェクトがシリアル化の対象であるかどうかをテストします。

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトをシリアル化できる場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

クラスをシリアル化できるようにするには、その宣言に [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) マクロを含める必要があります。また、実装には [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) マクロが含まれている必要があります。

> [!NOTE]
> この関数をオーバーライドしないでください。

### <a name="example"></a>例

すべての例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

## <a name="cobjectoperator-delete"></a><a name="operator_delete"></a> CObject:: operator delete

ライブラリのリリースバージョンでは、演算子 **`delete`** によって割り当てられたメモリが解放され **`new`** ます。

```cpp
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

デバッグバージョンでは、演算子は **`delete`** メモリリークを検出するように設計された割り当て監視スキームに参加します。

コード行を使用する場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

の実装の前。CPP ファイルを使用すると、の3番目のバージョンが **`delete`** 使用され、後でレポートできるように、割り当てられたブロックにファイル名と行番号が格納されます。 余分なパラメーターの指定について心配する必要はありません。これはマクロによって自動的に処理されます。

デバッグモードで DEBUG_NEW を使用しない場合でも、前に説明したソースファイルの行番号レポートがなくても、リーク検出は発生します。

演算子とをオーバーライドした場合は **`new`** **`delete`** 、この診断機能がプランます。

### <a name="example"></a>例

例で使用されているクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a> CObject:: operator new

ライブラリのリリースバージョンでは、演算子はと **`new`** 同様の方法で最適なメモリ割り当てを実行し `malloc` ます。

```cpp
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>解説

デバッグバージョンでは、演算子は **`new`** メモリリークを検出するように設計された割り当て監視スキームに参加します。

コード行を使用する場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

の実装の前。CPP ファイルを使用すると、の2番目のバージョンが **`new`** 使用され、後でレポートを作成するために、割り当てられたブロックにファイル名と行番号が格納されます。 余分なパラメーターの指定について心配する必要はありません。これはマクロによって自動的に処理されます。

デバッグモードで DEBUG_NEW を使用しない場合でも、前に説明したソースファイルの行番号レポートがなくても、リーク検出は発生します。

> [!NOTE]
> この演算子をオーバーライドする場合は、もオーバーライドする必要があり **`delete`** ます。 標準ライブラリ関数は使用しないで `_new_handler` ください。

### <a name="example"></a>例

例で使用されているクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a> CObject:: Serialize

アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
`CArchive`シリアル化または逆シリアル化するオブジェクト。

### <a name="remarks"></a>解説

を `Serialize` シリアル化する各クラスに対して、をオーバーライドする必要があります。 オーバーライドされたは、 `Serialize` まず `Serialize` 基底クラスの関数を呼び出す必要があります。

また、クラス宣言で [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) マクロを使用する必要があります。また、実装では、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) マクロを使用する必要があります。

[Carchive:: IsLoading](../../mfc/reference/carchive-class.md#isloading)または[Carchive:: isloading](../../mfc/reference/carchive-class.md#isstoring)を使用して、アーカイブが読み込み中であるか格納されているかを判断します。

`Serialize` は、 [carchive:: ReadObject](../../mfc/reference/carchive-class.md#readobject) および [Carchive:: WriteObject](../../mfc/reference/carchive-class.md#writeobject)によって呼び出されます。 これらの関数は、挿入演算子 () に関連付けられてい `CArchive` **<\<**) and extraction operator ( **>>** ます。

シリアル化の例については、「 [シリアル化: オブジェクト](../../mfc/serialization-serializing-an-object.md)のシリアル化」を参照してください。

### <a name="example"></a>例

すべての例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)
