---
title: 構造体
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: a58b9c97d5683423a0f81f6b5424f19f987943bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318557"
---
# <a name="cruntimeclass-structure"></a>構造体

派生`CObject`した各クラスは、実行時に`CRuntimeClass`オブジェクトまたはその基本クラスに関する情報を取得するために使用できる構造体に関連付けられます。

## <a name="syntax"></a>構文

```
struct CRuntimeClass
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クラス::オブジェクトの作成](#createobject)|実行時にオブジェクトを作成します。|
|[クラス::FromName](#fromname)|使い慣れたクラス名を使用して、実行時にオブジェクトを作成します。|
|[クラス::イズフロストから](#isderivedfrom)|クラスが指定したクラスから派生しているかどうかを判断します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[クラス:m_lpszClassName](#m_lpszclassname)|クラスの名前。|
|[ランタイムクラス::m_nObjectSize](#m_nobjectsize)|オブジェクトのサイズ (バイト単位)。|
|[ランタイムクラス::m_pBaseClass](#m_pbaseclass)|基本クラスの`CRuntimeClass`構造体へのポインター。|
|[ランタイムクラス::m_pfnCreateObject](#m_pfncreateobject)|オブジェクトを動的に作成する関数へのポインター。|
|[ランタイムクラス::m_pfnGetBaseClass](#m_pfngetbaseclass)|構造体を`CRuntimeClass`返します (動的にリンクされている場合のみ使用できます)。|
|[クラス:m_wSchema](#m_wschema)|クラスのスキーマ番号。|

## <a name="remarks"></a>解説

`CRuntimeClass`は構造体であるため、基本クラスはありません。

実行時にオブジェクトのクラスを判別する機能は、関数引数の追加の型チェックが必要な場合や、オブジェクトのクラスに基づいて特別な目的のコードを記述する必要がある場合に役立ちます。 ランタイム クラス情報は、C++ 言語で直接サポートされていません。

`CRuntimeClass`には、基本クラスへのポインターや関連クラス`CRuntimeClass`の ASCII クラス名など、関連する C++ オブジェクトに関する情報が提供されます。 この構造体は、オブジェクトの動的な作成、使い慣れた名前によるオブジェクトの型の指定、および関連クラスが特定のクラスから派生しているかどうかを判断するために使用できるさまざまな関数も実装します。

の使用方法`CRuntimeClass`の詳細については、「 ランタイム[クラス情報へのアクセス](../../mfc/accessing-run-time-class-information.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CRuntimeClass`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cruntimeclasscreateobject"></a><a name="createobject"></a>クラス::オブジェクトの作成

実行時に指定したクラスを動的に作成します。

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
作成するクラスの使い慣れた名前。

### <a name="return-value"></a>戻り値

新しく作成されたオブジェクトへのポインター、 または NULL クラス名が見つからないか、オブジェクトを作成するためのメモリが不足している場合。

### <a name="remarks"></a>解説

派生`CObject`したクラスは、実行時に指定したクラスのオブジェクトを作成する機能である動的作成をサポートできます。 たとえば、ドキュメント、ビュー、フレームの各クラスでは、動的な作成をサポートする必要があります。 動的作成とメンバーの`CreateObject`詳細については、「 CObject クラスおよび[CObject クラス : 機能レベルの指定](../../mfc/specifying-levels-of-functionality.md)」を参照してください。 [CObject Class](../../mfc/using-cobject.md)

### <a name="example"></a>例

  [「派生元」](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassfromname"></a><a name="fromname"></a>クラス::FromName

この関数を呼び出`CRuntimeClass`して、使い慣れた名前に関連付けられている構造体を取得します。

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
から`CObject`派生したクラスの使い慣れた名前。

### <a name="return-value"></a>戻り値

`CRuntimeClass` *lpszClassName*で渡される名前に対応するオブジェクトへのポインター。 一致するクラス名が見つからなかった場合、関数は NULL を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

## <a name="cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a>クラス::イズフロストから

呼び出し元のクラスが*pBaseClass*パラメーターで指定されたクラスから派生しているかどうかを確認します。

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
から`CObject`派生したクラスの使い慣れた名前。

### <a name="return-value"></a>戻り値

クラスの呼び出`IsDerivedFrom`しが、構造体が`CRuntimeClass`パラメーターとして指定されている基本クラスから派生する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

関係は、メンバーのクラスから派生クラスのチェーンを上から一番上まで上に"歩く"によって決定されます。 この関数は、基本クラスに一致するものが見つからない場合にのみ FALSE を返します。

> [!NOTE]
> 構造体を`CRuntimeClass`使用するには、実行時オブジェクト情報を取得するクラスの実装に、IMPLEMENT_DYNAMIC、IMPLEMENT_DYNCREATE、またはIMPLEMENT_SERIALマクロを含める必要があります。

の使用方法`CRuntimeClass`の詳細については、「 [CObject クラス : ランタイム クラス情報へのアクセス](../../mfc/accessing-run-time-class-information.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

## <a name="cruntimeclassm_lpszclassname"></a><a name="m_lpszclassname"></a>クラス:m_lpszClassName

ASCII クラス名を含む NULL で終わる文字列。

### <a name="remarks"></a>解説

この名前を使用して、メンバー関数を使用してクラスのインスタンス`FromName`を作成できます。

### <a name="example"></a>例

  [「派生元」](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassm_nobjectsize"></a><a name="m_nobjectsize"></a>ランタイムクラス::m_nObjectSize

オブジェクトのサイズ (バイト単位)。

### <a name="remarks"></a>解説

割り当てられたメモリを指すデータ メンバーがオブジェクトにある場合、そのメモリのサイズは含まれません。

### <a name="example"></a>例

  [「派生元」](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassm_pbaseclass"></a><a name="m_pbaseclass"></a>ランタイムクラス::m_pBaseClass

アプリケーションが MFC に静的にリンクしている場合、このデータ メンバーには`CRuntimeClass`基本クラスの構造体へのポインターが含まれます。

### <a name="remarks"></a>解説

アプリケーションが MFC ライブラリに動的にリンクしている場合は[、「m_pfnGetBaseClass」](#m_pfngetbaseclass)を参照してください。

### <a name="example"></a>例

  [「派生元」](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassm_pfncreateobject"></a><a name="m_pfncreateobject"></a>ランタイムクラス::m_pfnCreateObject

クラスのオブジェクトを作成する既定のコンストラクターへの関数ポインター。

### <a name="remarks"></a>解説

このポインターは、クラスが動的作成をサポートしている場合にのみ有効です。それ以外の場合、関数は NULL を返します。

## <a name="cruntimeclassm_pfngetbaseclass"></a><a name="m_pfngetbaseclass"></a>ランタイムクラス::m_pfnGetBaseClass

アプリケーションで MFC ライブラリを共有 DLL として使用する場合、このデータ メンバーは基本`CRuntimeClass`クラスの構造体を返す関数を指します。

### <a name="remarks"></a>解説

アプリケーションが MFC ライブラリに静的にリンクしている場合は[、「m_pBaseClass」](#m_pbaseclass)を参照してください。

### <a name="example"></a>例

  [「派生元」](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassm_wschema"></a><a name="m_wschema"></a>クラス:m_wSchema

スキーマ番号 ( シリアル化できないクラスの場合は -1)

### <a name="remarks"></a>解説

スキーマ番号の詳細については[、IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロを参照してください。

### <a name="example"></a>例

  [「派生元」](#isderivedfrom)の例を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスを取得します。](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[オブジェクト::イズキンドフ](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
