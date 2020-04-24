---
title: Cオブジェクトクラス
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
ms.openlocfilehash: 66d76e0062d13b2bd5a16d9b07f99db9e989805a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753994"
---
# <a name="cobject-class"></a>Cオブジェクトクラス

MFC ライブラリの重要な基底クラスです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CObject
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[Cオブジェクト::Cオブジェクト](#cobject)|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cオブジェクト::アサートValid](#assertvalid)|このオブジェクトの整合性を検証します。|
|[オブジェクト::Dウンプ](#dump)|このオブジェクトの診断ダンプを生成します。|
|[クラスを取得します。](#getruntimeclass)|このオブジェクト`CRuntimeClass`のクラスに対応する構造体を返します。|
|[オブジェクト::イズキンドフ](#iskindof)|このオブジェクトと特定のクラスとの関係をテストします。|
|[Cオブジェクト::シリアル化可能](#isserializable)|このオブジェクトをシリアル化できるかどうかをテストします。|
|[Cオブジェクト::シリアライズ](#serialize)|アーカイブからオブジェクトを読み込むか、アーカイブに格納します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cオブジェクト::オペレータ削除](#operator_delete)|特殊な**削除**演算子。|
|[Cオブジェクト::オペレータ新しい](#operator_new)|特別な**新しい**オペレータ。|

## <a name="remarks"></a>解説

これは、 などの`CFile`ライブラリ クラスだけでなく、`CObList`作成するクラスのルートとしても機能します。 `CObject`を含む基本的なサービスを提供します。

- シリアル化のサポート

- ランタイム クラス情報

- オブジェクト診断出力

- コレクション クラスとの互換性

多重`CObject`継承はサポートされていません。 派生クラスは 1 つの`CObject`基本クラスしか持て`CObject`ず、階層内で一番左にする必要があります。 ただし、右側の多重継承分岐に構造体と非`CObject`派生クラスを持つことは許されます。

クラスの実装と宣言で`CObject`オプションのマクロを使用すると、派生から大きなメリットが得られます。

第 1 レベルのマクロ[(DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)と[IMPLEMENT_DYNAMIC)](run-time-object-model-services.md#implement_dynamic)では、クラス名と階層内での位置へのランタイム アクセスが許可されます。 これにより、意味のある診断ダンプが可能になります。

第 2 レベルのマクロ[(DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)と[IMPLEMENT_SERIAL)](run-time-object-model-services.md#implement_serial)には、第 1 レベルのマクロのすべての機能が含まれ、オブジェクトを "アーカイブ" との間で "シリアル化" できます。

Microsoft Foundation クラスと C++ クラスの一般的な派生`CObject`方法と を使用する方法については、「 [CObject](../../mfc/using-cobject.md)と[シリアル化](../../mfc/serialization-in-mfc.md)の使用 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cobjectassertvalid"></a><a name="assertvalid"></a>Cオブジェクト::アサートValid

このオブジェクトの整合性を検証します。

```
virtual void AssertValid() const;
```

### <a name="remarks"></a>解説

`AssertValid`内部状態をチェックすることによって、このオブジェクトの妥当性検査を実行します。 ライブラリのデバッグ バージョンでは、`AssertValid`アサーションが失敗した行番号とファイル名を示すメッセージを使用してプログラムをアサートし、終了する場合があります。

独自のクラスを作成する場合は、関数を`AssertValid`オーバーライドして、自分自身およびクラスの他のユーザーに診断サービスを提供する必要があります。 オーバーライドは`AssertValid`、通常、派生`AssertValid`クラスに固有のデータ メンバーをチェックする前に、基本クラスの関数を呼び出します。

const`AssertValid`関数**const**であるため、テスト中にオブジェクトの状態を変更することはできません。 独自の派生クラス`AssertValid`関数は、例外をスローするのではなく、無効なオブジェクト データを検出するかどうかをアサートする必要があります。

「有効性」の定義は、オブジェクトのクラスによって異なります。 原則として、関数は「浅いチェック」を実行する必要があります。 つまり、オブジェクトに他のオブジェクトへのポインターが含まれている場合、ポインターが null でないかどうかをチェックする必要がありますが、ポインターによって参照されるオブジェクトに対して妥当性検査を実行すべきではありません。

### <a name="example"></a>例

すべての`CObject`例で使用されるクラスのリストについては[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCObjectSample#7](../../mfc/codesnippet/cpp/cobject-class_1.cpp)]

別の例については、「 [AfxDoForAllObjects](diagnostic-services.md#afxdoforallobjects)」を参照してください。

## <a name="cobjectcobject"></a><a name="cobject"></a>Cオブジェクト::Cオブジェクト

これらの関数は、標準`CObject`のコンストラクターです。

```
CObject();
CObject(const CObject& objectSrc);
```

### <a name="parameters"></a>パラメーター

*オブジェクトSrc*<br/>
別の参照への参照`CObject`

### <a name="remarks"></a>解説

既定のバージョンは、派生クラスのコンストラクターによって自動的に呼び出されます。

クラスがシリアル化可能な場合 (IMPLEMENT_SERIAL マクロが組み込まれています)、クラス宣言に既定のコンストラクター (引数のないコンストラクター) が必要です。 既定のコンストラクターが必要ない場合は、プライベート コンストラクターまたは保護された "空" コンストラクターを宣言します。 詳細については、「 [CObject](../../mfc/using-cobject.md)の使用 」を参照してください。

標準の C++ クラス コピー コンストラクターは、メンバーごとのコピーを行います。 プライベート`CObject`コピー コンストラクターが存在すると、クラスのコピー コンストラクターが必要だが使用できない場合に、コンパイラ エラー メッセージが保証されます。 したがって、クラスがこの機能を必要とする場合は、コピー コンストラクターを指定する必要があります。

### <a name="example"></a>例

例で使用されているクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge``CObject`参照してください。

[!code-cpp[NVC_MFCCObjectSample#8](../../mfc/codesnippet/cpp/cobject-class_2.cpp)]

## <a name="cobjectdump"></a><a name="dump"></a>オブジェクト::Dウンプ

オブジェクトの内容を[CDumpContext](../../mfc/reference/cdumpcontext-class.md)オブジェクトにダンプします。

```
virtual void Dump(CDumpContext& dc) const;
```

### <a name="parameters"></a>パラメーター

*Dc*<br/>
ダンプの診断ダンプ コンテキスト (通常`afxDump`.

### <a name="remarks"></a>解説

独自のクラスを作成する場合は、関数を`Dump`オーバーライドして、自分自身およびクラスの他のユーザーに診断サービスを提供する必要があります。 オーバーライドは`Dump`、通常、派生`Dump`クラスに固有のデータ メンバーを印刷する前に、基本クラスの関数を呼び出します。 `CObject::Dump`クラスが マクロまたは IMPLEMENT_SERIAL マクロ`IMPLEMENT_DYNAMIC`を使用している場合は、クラス名を出力します。

> [!NOTE]
> 関数`Dump`は、出力の最後に改行文字を出力しないでください。

`Dump`呼び出しは、Microsoft Foundation クラス ライブラリのデバッグ バージョンでのみ意味をなします。 条件付きコンパイルの_DEBUG/ `#endif`ステートメント**を使用**して、呼び出し、関数宣言、関数の実装#ifdef角かっこで囲む必要があります。

const`Dump`関数**const**なので、ダンプ中にオブジェクトの状態を変更することはできません。

[CDumpContext 挿入 (<<)](../../mfc/reference/cdumpcontext-class.md#operator_lt_lt) `Dump`演算子は`CObject`、ポインターが挿入されたときに呼び出します。

`Dump`は、オブジェクトの「非循環」ダンプのみを許可します。 たとえば、オブジェクトのリストをダンプできますが、オブジェクトの 1 つがリスト自体である場合、最終的にはスタックをオーバーフローします。

### <a name="example"></a>例

すべての`CObject`例で使用されるクラスのリストについては[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCObjectSample#9](../../mfc/codesnippet/cpp/cobject-class_3.cpp)]

## <a name="cobjectgetruntimeclass"></a><a name="getruntimeclass"></a>クラスを取得します。

このオブジェクト`CRuntimeClass`のクラスに対応する構造体を返します。

```
virtual CRuntimeClass* GetRuntimeClass() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトのクラスに対応する[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。決して**NULL .**

### <a name="remarks"></a>解説

派生クラスごとに`CRuntimeClass``CObject`1 つの構造体があります。 構造体のメンバーは次のとおりです。

- **m_lpszClassName**ASCII クラス名を含む NULL で終わる文字列。

- **int m_nObjectSize**オブジェクトのサイズ (バイト単位)。 割り当てられたメモリを指すデータ メンバーがオブジェクトにある場合、そのメモリのサイズは含まれません。

- **ウイントm_wSchema**スキーマ番号 ( - 1 シリアル化できないクラスの場合) スキーマ番号の説明については[、IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロを参照してください。

- **CObject\* (\* PASCAL m_pfnCreateObject ) ( )** クラスのオブジェクトを作成するデフォルトのコンストラクタへの関数ポインタ (クラスが動的作成をサポート**NULL**している場合にのみ有効です。

- **CRuntimeClass\* (\* PASCAL m_pfn_GetBaseClass ) ) アプリケーション**が AFXDLL バージョンの MFC に動的にリンクされている場合は、基本クラスの構造体を`CRuntimeClass`返す関数へのポインター。

- **CRuntimeClass\* m_pBaseClass**アプリケーションが MFC に静的にリンクされている場合は、`CRuntimeClass`基本クラスの構造体へのポインター。

この関数では、クラス実装で[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)、 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)、または[マクロIMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)使用する必要があります。 そうでなければ、正しくない結果が得られます。

### <a name="example"></a>例

すべての`CObject`例で使用されるクラスのリストについては[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCObjectSample#10](../../mfc/codesnippet/cpp/cobject-class_4.cpp)]

## <a name="cobjectiskindof"></a><a name="iskindof"></a>オブジェクト::イズキンドフ

このオブジェクトと特定のクラスとの関係をテストします。

```
BOOL IsKindOf(const CRuntimeClass* pClass) const;
```

### <a name="parameters"></a>パラメーター

*Pclass*<br/>
派生クラスに関連付けられた[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) `CObject`構造体へのポインター。

### <a name="return-value"></a>戻り値

オブジェクトがクラスに対応する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は *、(1)* 指定したクラスのオブジェクトであるか 、(2) 指定されたクラスから派生したクラスのオブジェクトであるかどうかを調べたい pClass をテストします。 この関数は、 [、](run-time-object-model-services.md#declare_dyncreate)DECLARE_DYNCREATE マクロ 、または マクロ[DECLARE_DYNAMIC](run-time-object-model-services.md#declare_dynamic)で宣言されたクラスでのみ機能[DECLARE_SERIAL。](run-time-object-model-services.md#declare_serial)

この関数は C++ ポリモーフィズム機能を使用しないため、広範囲に使用しないでください。 代わりに仮想関数を使用してください。

### <a name="example"></a>例

すべての`CObject`例で使用されるクラスのリストについては[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCObjectSample#11](../../mfc/codesnippet/cpp/cobject-class_5.cpp)]

## <a name="cobjectisserializable"></a><a name="isserializable"></a>Cオブジェクト::シリアル化可能

このオブジェクトがシリアル化に適しているかどうかをテストします。

```
BOOL IsSerializable() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトをシリアル化できる場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

クラスをシリアル化できるようにするには、その宣言に[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロが含まれ、実装に[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロが含まれている必要があります。

> [!NOTE]
> この関数をオーバーライドしないでください。

### <a name="example"></a>例

すべての`CObject`例で使用されるクラスのリストについては[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCObjectSample#12](../../mfc/codesnippet/cpp/cobject-class_6.cpp)]

## <a name="cobjectoperator-delete"></a><a name="operator_delete"></a>Cオブジェクト::オペレータ削除

ライブラリのリリース バージョンの場合、演算子**delete**は、演算子**new**によって割り当てられたメモリを解放します。

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

デバッグ バージョンでは、オペレーター**の delete**は、メモリ リークを検出するために設計された割り当て監視スキームに参加します。

コード行を使用する場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

での実装の前に.CPP ファイルを使用すると、削除**の**3 番目のバージョンが使用され、後でレポートするために割り当てられたブロックにファイル名と行番号が格納されます。 余分なパラメータを指定する心配はありません。マクロがあなたのためにそれを処理します。

デバッグ モードでDEBUG_NEWを使用しない場合でも、リーク検出は行われますが、上記のソース ファイル行番号レポートは表示されません。

演算子を**新規**にオーバーライドして**削除**すると、この診断機能は失われます。

### <a name="example"></a>例

例で使用されているクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge``CObject`参照してください。

[!code-cpp[NVC_MFCCObjectSample#15](../../mfc/codesnippet/cpp/cobject-class_8.cpp)]

## <a name="cobjectoperator-new"></a><a name="operator_new"></a>Cオブジェクト::オペレータ新しい

ライブラリのリリース バージョンでは、演算子**new**は、次のような方法で最適なメモリ`malloc`割り当てを実行します。

```cpp
void* PASCAL operator new(size_t nSize);
void* PASCAL operator new(size_t, void* p);

void* PASCAL operator new(
    size_t nSize,
    LPCSTR lpszFileName,
    int nLine);
```

### <a name="remarks"></a>解説

デバッグ バージョンでは、オペレータ**new**はメモリ リークを検出するために設計された割り当て監視スキームに参加します。

コード行を使用する場合

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/cobject-class_7.cpp)]

での実装の前に.CPP ファイルを使用すると、新**しい**の 2 番目のバージョンが使用され、後でレポートするために割り当てられたブロックにファイル名と行番号が格納されます。 余分なパラメータを指定する心配はありません。マクロがあなたのためにそれを処理します。

デバッグ モードでDEBUG_NEWを使用しない場合でも、リーク検出は行われますが、上記のソース ファイル行番号レポートは表示されません。

> [!NOTE]
> この演算子をオーバーライドする場合は、 **delete**もオーバーライドする必要があります。 標準ライブラリ`_new_handler`関数は使用しないでください。

### <a name="example"></a>例

例で使用されているクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge``CObject`参照してください。

[!code-cpp[NVC_MFCCObjectSample#16](../../mfc/codesnippet/cpp/cobject-class_9.h)]

## <a name="cobjectserialize"></a><a name="serialize"></a>Cオブジェクト::シリアライズ

アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
シリアル`CArchive`化するオブジェクトまたはシリアル化するオブジェクト。

### <a name="remarks"></a>解説

シリアル化する`Serialize`クラスごとにオーバーライドする必要があります。 オーバーライドされた場合`Serialize`は、まずその`Serialize`基本クラスの関数を呼び出す必要があります。

クラス宣言で[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロも使用し、実装で[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロを使用する必要があります。

[アーカイブが読み込みまたは保存されているかどうかを判断するには、CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading)または[CArchive::Is格納](../../mfc/reference/carchive-class.md#isstoring)を使用します。

`Serialize`は、C アーカイブによって呼び出されます:[読み取りオブジェクト](../../mfc/reference/carchive-class.md#readobject)と[C アーカイブ::書き込みオブジェクト](../../mfc/reference/carchive-class.md#writeobject). これらの関数は`CArchive`、挿入演算子 ( ** < **) と抽出演算子**>>**( ) に関連付けられます。

シリアル化の例については、「[シリアル化: オブジェクトのシリアル化](../../mfc/serialization-serializing-an-object.md)」を参照してください。

### <a name="example"></a>例

すべての`CObject`例で使用されるクラスのリストについては[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCObjectSample#13](../../mfc/codesnippet/cpp/cobject-class_10.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)
