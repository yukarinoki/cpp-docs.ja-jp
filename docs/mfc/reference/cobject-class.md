---
description: '詳細: CObject クラス'
title: CObject クラス
ms.date: 1/12/2021
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
ms.openlocfilehash: ba152a9cbbe6e2fa217d6c2e24d13ea48dd37c87
ms.sourcegitcommit: b51f79b5394e12cd90cb65c85cc01716f90bfc90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "98167009"
---
# <a name="cobject-class"></a>`CObject` クラス

MFC ライブラリの重要な基底クラスです。

## <a name="syntax"></a>構文

```cpp
class AFX_NOVTABLE CObject
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[`CObject::CObject`](#cobject)|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[`CObject::AssertValid`](#assertvalid)|このオブジェクトの整合性を検証します。|
|[`CObject::Dump`](#dump)|このオブジェクトの診断ダンプを生成します。|
|[`CObject::GetRuntimeClass`](#getruntimeclass)|`CRuntimeClass`このオブジェクトのクラスに対応する構造体を返します。|
|[`CObject::IsKindOf`](#iskindof)|このオブジェクトと特定のクラスとの関係をテストします。|
|[`CObject::IsSerializable`](#isserializable)|このオブジェクトをシリアル化できるかどうかをテストします。|
|[`CObject::Serialize`](#serialize)|アーカイブからのオブジェクトの読み込みまたは保存を行います。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[`CObject::operator delete`](#operator_delete)|特別な **`delete`** 演算子。|
|[`CObject::operator new`](#operator_new)|特別な **`new`** 演算子。|

## <a name="remarks"></a>Remarks

これは、やなどのライブラリクラスだけでなく、記述するクラスのルートとしても機能し `CFile` `CObList` ます。 `CObject` 基本的なサービスを提供します。

- シリアル化のサポート
- ランタイムクラス情報
- オブジェクトの診断出力
- コレクションクラスとの互換性

`CObject` は複数の継承をサポートしていません。 派生クラスは基底クラスを1つだけ持つことができ、 `CObject` `CObject` 階層の最上位にある必要があります。 ただし、構造と非 `CObject` 派生クラスを右側の複数継承分岐に含めることは許可されています。

`CObject`クラスの実装と宣言で省略可能なマクロの一部を使用すると、派生の大きな利点が得られます。

第1レベルのマクロ、 [`DECLARE_DYNAMIC`](run-time-object-model-services.md#declare_dynamic) および [`IMPLEMENT_DYNAMIC`](run-time-object-model-services.md#implement_dynamic) では、階層内のクラス名とその位置への実行時アクセスが許可されます。 これにより、意味のある診断ダンプを行うことができます。

第2レベルのマクロとには、 [`DECLARE_SERIAL`](run-time-object-model-services.md#declare_serial) [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial) 第1レベルのマクロのすべての機能が含まれています。また、"アーカイブ" との間でオブジェクトを "シリアル化" できるようにします。

一般的な、およびを使用した Microsoft Foundation classes と C++ クラスの派生の詳細について `CObject` は、「 [CObject](../../mfc/using-cobject.md) と [シリアル化](../../mfc/serialization-in-mfc.md)の使用」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CObject`

## <a name="requirements"></a>必要条件

**ヘッダー:**`afx.h`

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a> CObject:: AssertValid

このオブジェクトの整合性を検証します。

```cpp
virtual void AssertValid() const;
```

### <a name="remarks"></a>Remarks

`AssertValid` 内部状態を確認することにより、このオブジェクトの有効性チェックを実行します。 ライブラリのデバッグバージョンでは、は `AssertValid` アサートしてから、アサーションが失敗した行番号とファイル名を一覧表示するメッセージを使用してプログラムを終了する場合があります。

独自のクラスを記述する場合は、関数をオーバーライドして、 `AssertValid` 自分やクラスの他のユーザーに診断サービスを提供する必要があります。 通常、オーバーライドされたは、 `AssertValid` `AssertValid` 派生クラスに固有のデータメンバーをチェックする前に、基本クラスの関数を呼び出します。

は関数であるため `AssertValid` **`const`** 、テスト中にオブジェクトの状態を変更することはできません。 独自の派生クラス `AssertValid` 関数は、例外をスローするのではなく、無効なオブジェクトデータを検出するかどうかをアサートする必要があります。

"有効性" の定義は、オブジェクトのクラスによって異なります。 ルールとして、関数は "浅いチェック" を行う必要があります。 つまり、オブジェクトに他のオブジェクトへのポインターが含まれている場合は、ポインターが存在しないかどうかを確認する必要があり `NULL` ますが、ポインターによって参照されているオブジェクトに対して有効性テストを実行することはできません。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` すべての例で使用されるクラスの一覧については、「」を参照してください `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

別の例については、「」を参照してください [`AfxDoForAllObjects`](diagnostic-services.md#afxdoforallobjects) 。

## <a name="cobjectcobject"></a><a name="cobject"></a> CObject:: CObject

これらの関数は、標準 `CObject` コンストラクターです。

```cpp
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>パラメーター

*objectSrc*\
別のへの参照 `CObject`

### <a name="remarks"></a>Remarks

既定のバージョンは、派生クラスのコンストラクターによって自動的に呼び出されます。

クラスがシリアル化可能である (マクロが組み込まれている) 場合は `IMPLEMENT_SERIAL` 、クラス宣言に既定のコンストラクター (引数なしのコンストラクター) が必要です。 既定のコンストラクターが不要な場合は、プライベートまたは保護された "空の" コンストラクターを宣言します。 詳細については、「 [Using `CObject` ](../../mfc/using-cobject.md)」を参照してください。

標準 C++ の既定のクラスコピーコンストラクターは、メンバーごとのコピーを行います。 プライベートコピーコンストラクターが存在することは、 `CObject` クラスのコピーコンストラクターが必要であるが使用できない場合に、コンパイラエラーメッセージを保証します。 クラスにこの機能が必要な場合は、コピーコンストラクターを指定します。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` 例で使用されているクラスの一覧については、「」を参照してください `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a> CObject::D ump

オブジェクトのコンテンツをオブジェクトにダンプし [`CDumpContext`](../../mfc/reference/cdumpcontext-class.md) ます。

```cpp
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>パラメーター

*修飾*\
ダンプの診断ダンプコンテキスト (通常は) `afxDump` 。

### <a name="remarks"></a>Remarks

独自のクラスを記述する場合は、関数をオーバーライドして、 `Dump` 自分やクラスの他のユーザーに診断サービスを提供する必要があります。 通常、オーバーライドされたは、 `Dump` `Dump` 派生クラスに固有のデータメンバーを出力する前に、基本クラスの関数を呼び出します。 `CObject::Dump` クラスでマクロまたはマクロを使用する場合は、クラス名を出力し `IMPLEMENT_DYNAMIC` `IMPLEMENT_SERIAL` ます。

> [!NOTE]
> `Dump`関数は、出力の末尾に改行文字を出力しません。

`Dump` 呼び出しは、Microsoft Foundation Class ライブラリのデバッグバージョンでのみ意味があります。 呼び出し、関数宣言、および関数の実装は `#ifdef _DEBUG` 、 `#endif` 条件付きコンパイルのステートメントを使用して、かっこで囲む必要があります。

は関数であるため `Dump` **`const`** 、ダンプ中にオブジェクトの状態を変更することはできません。

[ `CDumpContext` 挿入 (<<) 演算子](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt)は、 `Dump` ポインターが挿入されたときにを呼び出し `CObject` ます。

`Dump` オブジェクトの "非循環" ダンプのみを許可します。 たとえば、オブジェクトの一覧をダンプできますが、オブジェクトの1つがリスト自体の場合は、最終的にスタックをオーバーフローします。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` すべての例で使用されるクラスの一覧については、「」を参照してください `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a> CObject:: GetRuntimeClass

`CRuntimeClass`このオブジェクトのクラスに対応する構造体を返します。

```cpp
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>戻り値

[`CRuntimeClass`](../../mfc/reference/cruntimeclass-structure.md)このオブジェクトのクラスに対応する構造体へのポインター。 **`NULL`** できません。

### <a name="remarks"></a>Remarks

`CRuntimeClass`各派生クラスには1つの構造体があり `CObject` ます。 構造体のメンバーは次のとおりです。

- **`LPCSTR m_lpszClassName`** ASCII クラス名を格納している null で終わる文字列。
- **`int m_nObjectSize`** オブジェクトのサイズ (バイト単位)。 割り当てられたメモリを指すデータメンバーがオブジェクトに含まれている場合、そのメモリのサイズは含まれません。
- **`UINT m_wSchema`** スキーマ番号 (シリアル化クラスの場合は-1)。 [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial)スキーマ番号の説明については、マクロを参照してください。

- **`CObject* (PASCAL* m_pfnCreateObject)()`** クラスのオブジェクトを作成する既定のコンストラクターへの関数ポインター (クラスが動的作成をサポートしている場合にのみ有効)。それ以外の場合、はを返し **`NULL`** ます。

- **`CRuntimeClass* (PASCAL* m_pfn_GetBaseClass )()`** アプリケーションが AFXDLL バージョンの MFC に動的にリンクされている場合は、 `CRuntimeClass` 基本クラスの構造体を返す関数へのポインター。

- **`CRuntimeClass* m_pBaseClass`** アプリケーションが MFC に静的にリンクされている場合は、 `CRuntimeClass` 基本クラスの構造体へのポインター。

この関数 [`IMPLEMENT_DYNAMIC`](run-time-object-model-services.md#implement_dynamic) では、クラスの [`IMPLEMENT_DYNCREATE`](run-time-object-model-services.md#implement_dyncreate) 実装で、、またはマクロを使用する必要があり [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial) ます。 それ以外の場合は、正しくない結果が返されます。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` すべての例で使用されるクラスの一覧については、「」を参照してください `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a> CObject:: IsKindOf

このオブジェクトと特定のクラスとの関係をテストします。

```cpp
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>パラメーター

*`pClass`*\
[`CRuntimeClass`](../../mfc/reference/cruntimeclass-structure.md)派生クラスに関連付けられている構造体へのポインター `CObject` 。

### <a name="return-value"></a>戻り値

オブジェクトがクラスに対応している場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

この関数 *`pClass`* は、(1) が指定されたクラスのオブジェクトであるか (2)、指定されたクラスから派生したクラスのオブジェクトであるかどうかをテストします。 この関数は [`DECLARE_DYNAMIC`](run-time-object-model-services.md#declare_dynamic) 、、、またはマクロで宣言されたクラスに対してのみ機能 [`DECLARE_DYNCREATE`](run-time-object-model-services.md#declare_dyncreate) [`DECLARE_SERIAL`](run-time-object-model-services.md#declare_serial) します。

C++ のポリモーフィズム機能を損なうため、この関数は広く使用しないでください。 代わりに仮想関数を使用してください。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` すべての例で使用されるクラスの一覧については、「」を参照してください `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a> CObject:: IsSerializable

このオブジェクトがシリアル化の対象であるかどうかをテストします。

```cpp
BOOL IsSerializable() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトをシリアル化できる場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

クラスをシリアル化できるようにするには、その宣言にマクロが含まれている必要があり [`DECLARE_SERIAL`](run-time-object-model-services.md#declare_serial) ます。また、実装にマクロが含まれている必要があり [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial) ます。

> [!NOTE]
> この関数はオーバーライドしないでください。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` すべての例で使用されるクラスの一覧については、「」を参照してください `CObject` 。

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

### <a name="remarks"></a>Remarks

デバッグバージョンでは、演算子は **`delete`** メモリリークを検出するように設計された割り当て監視スキームに参加します。

コード行を使用する場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

の実装の前。CPP ファイルを使用すると、の3番目のバージョンが **`delete`** 使用され、後でレポートできるように、割り当てられたブロックにファイル名と行番号が格納されます。 余分なパラメーターの指定について心配する必要はありません。これはマクロによって自動的に処理されます。

デバッグモードでを使用しない場合でも `DEBUG_NEW` 、前に説明したソースファイルの行番号レポートがなくても、リーク検出は発生します。

演算子とをオーバーライドした場合は **`new`** **`delete`** 、この診断機能がプランます。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` 例で使用されているクラスの一覧については、「」を参照してください `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a> CObject:: operator new

ライブラリのリリースバージョンでは、演算子 **`new`** はと同様の方法で最適なメモリ割り当てを行い `malloc` ます。

```cpp
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>Remarks

デバッグバージョンでは、演算子は **`new`** メモリリークを検出するように設計された割り当て監視スキームに参加します。

コード行を使用する場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

の実装の前。CPP ファイルを使用すると、の2番目のバージョンが **`new`** 使用され、後でレポートを作成するために、割り当てられたブロックにファイル名と行番号が格納されます。 余分なパラメーターの指定について心配する必要はありません。これはマクロによって自動的に処理されます。

デバッグモードでを使用しない場合でも `DEBUG_NEW` 、前に説明したソースファイルの行番号レポートがなくても、リーク検出は発生します。

> [!NOTE]
> この演算子をオーバーライドする場合は、もオーバーライドする必要があり **`delete`** ます。 標準ライブラリ関数は使用しないで `_new_handler` ください。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` 例で使用されているクラスの一覧については、「」を参照してください `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a> CObject:: Serialize

アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。

```cpp
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*`ar`*\
`CArchive`シリアル化または逆シリアル化するオブジェクト。

### <a name="remarks"></a>Remarks

`Serialize`シリアル化する各クラスのをオーバーライドします。 オーバーライドされたは、 `Serialize` まず `Serialize` 基底クラスの関数を呼び出す必要があります。

また、クラス宣言でマクロを使用する必要があり、 [`DECLARE_SERIAL`](run-time-object-model-services.md#declare_serial) 実装でマクロを使用する必要があり [`IMPLEMENT_SERIAL`](run-time-object-model-services.md#implement_serial) ます。

[`CArchive::IsLoading`](../../mfc/reference/carchive-class.md#isloading)または [`CArchive::IsStoring`](../../mfc/reference/carchive-class.md#isstoring) を使用して、アーカイブが読み込み中であるか格納されているかを判断します。

`Serialize` は、およびによって呼び出され [`CArchive::ReadObject`](../../mfc/reference/carchive-class.md#readobject) [`CArchive::WriteObject`](../../mfc/reference/carchive-class.md#writeobject) ます。 これらの関数は、 `CArchive` 挿入演算子 ( **`<<`** ) と抽出演算子 () に関連付けられてい **`>>`** ます。

シリアル化の例については、「 [オブジェクトのシリアル](../../mfc/serialization-serializing-an-object.md)化」を参照してください。

### <a name="example"></a>例

[`CObList::CObList`](../../mfc/reference/coblist-class.md#coblist) `CAge` すべての例で使用されるクラスの一覧については、「」を参照してください `CObject` 。

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)
