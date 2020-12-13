---
description: '詳細については、次を参照してください: CRuntimeClass 構造体'
title: CRuntimeClass 構造体
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: e02732ec595026f028ad4b8f9bd3d8898a40cbc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342918"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass 構造体

から派生した各クラス `CObject` は、 `CRuntimeClass` 実行時にオブジェクトまたはその基本クラスに関する情報を取得するために使用できる構造体に関連付けられています。

## <a name="syntax"></a>構文

```
struct CRuntimeClass
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRuntimeClass:: CreateObject](#createobject)|実行時にオブジェクトを作成します。|
|[CRuntimeClass:: FromName](#fromname)|使い慣れたクラス名を使用して、実行時にオブジェクトを作成します。|
|[CRuntimeClass:: IsDerivedFrom](#isderivedfrom)|指定したクラスから派生したクラスかどうかを判断します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CRuntimeClass:: m_lpszClassName](#m_lpszclassname)|クラスの名前。|
|[CRuntimeClass:: m_nObjectSize](#m_nobjectsize)|オブジェクトのサイズ (バイト単位)。|
|[CRuntimeClass:: m_pBaseClass](#m_pbaseclass)|`CRuntimeClass`基底クラスの構造体へのポインター。|
|[CRuntimeClass:: m_pfnCreateObject](#m_pfncreateobject)|オブジェクトを動的に作成する関数へのポインター。|
|[CRuntimeClass:: m_pfnGetBaseClass](#m_pfngetbaseclass)|`CRuntimeClass`構造体を返します (動的にリンクされている場合にのみ使用できます)。|
|[CRuntimeClass:: m_wSchema](#m_wschema)|クラスのスキーマ番号。|

## <a name="remarks"></a>解説

`CRuntimeClass` は構造体であるため、基底クラスを持ちません。

実行時にオブジェクトのクラスを決定する機能は、関数の引数の追加の型チェックが必要な場合、またはオブジェクトのクラスに基づいて特殊な目的のコードを記述する必要がある場合に便利です。 ランタイムクラス情報は、C++ 言語で直接サポートされていません。

`CRuntimeClass``CRuntimeClass`基底クラスのへのポインターや関連クラスの ASCII クラス名など、関連する C++ オブジェクトに関する情報を提供します。 この構造体には、オブジェクトを動的に作成したり、使い慣れた名前を使用してオブジェクトの型を指定したり、関連するクラスが特定のクラスから派生したかどうかを判断したりするために使用できるさまざまな関数も実装されています。

の使用方法の詳細については `CRuntimeClass` 、 [Run-Time クラス情報へのアクセス](../../mfc/accessing-run-time-class-information.md)に関する記事を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CRuntimeClass`

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="cruntimeclasscreateobject"></a><a name="createobject"></a> CRuntimeClass:: CreateObject

実行時に指定したクラスを動的に作成するには、この関数を呼び出します。

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>パラメーター

*lpszClassName*<br/>
作成されるクラスの使い慣れた名前。

### <a name="return-value"></a>戻り値

新しく作成されたオブジェクトへのポインター。クラス名が見つからない場合、またはオブジェクトを作成するためのメモリが不足している場合は NULL。

### <a name="remarks"></a>解説

から派生し `CObject` たクラスは動的作成をサポートできます。これは、実行時に指定したクラスのオブジェクトを作成する機能です。 たとえば、ドキュメント、ビュー、およびフレームクラスでは、動的作成がサポートされている必要があります。 動的作成とメンバーの詳細につい `CreateObject` ては、「 [cobject クラス](../../mfc/using-cobject.md) と [cobject クラス: 機能のレベルの指定](../../mfc/specifying-levels-of-functionality.md)」を参照してください。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassfromname"></a><a name="fromname"></a> CRuntimeClass:: FromName

この関数を呼び出して、 `CRuntimeClass` 使い慣れた名前に関連付けられている構造体を取得します。

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>パラメーター

*lpszClassName*<br/>
から派生したクラスのわかりやすい名前 `CObject` 。

### <a name="return-value"></a>戻り値

`CRuntimeClass` *Lpszclassname* で渡された名前に対応するオブジェクトへのポインター。 一致するクラス名が見つからなかった場合、関数は NULL を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

## <a name="cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a> CRuntimeClass:: IsDerivedFrom

この関数を呼び出して、 *pBaseClass* パラメーターで指定したクラスから呼び出し元のクラスが派生しているかどうかを確認します。

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>パラメーター

*pBaseClass*<br/>
から派生したクラスのわかりやすい名前 `CObject` 。

### <a name="return-value"></a>戻り値

を呼び出すクラス `IsDerivedFrom` が基本クラスから派生し、その `CRuntimeClass` 構造体がパラメーターとして指定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

リレーションシップは、メンバーのクラスの "ウォーキング" によって、最上位に至るまでの派生クラスのチェーンによって決定されます。 この関数は、基底クラスの一致が検出されない場合にのみ、FALSE を返します。

> [!NOTE]
> 構造体を使用するには、 `CRuntimeClass` 実行時オブジェクト情報を取得するクラスの実装に、IMPLEMENT_DYNAMIC、IMPLEMENT_DYNCREATE、または IMPLEMENT_SERIAL マクロを含める必要があります。

の使用方法の詳細については `CRuntimeClass` 、「 [CObject クラス: Run-Time クラス情報へのアクセス](../../mfc/accessing-run-time-class-information.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

## <a name="cruntimeclassm_lpszclassname"></a><a name="m_lpszclassname"></a> CRuntimeClass:: m_lpszClassName

ASCII クラス名を格納している null で終わる文字列。

### <a name="remarks"></a>解説

この名前は、メンバー関数を使用してクラスのインスタンスを作成するために使用でき `FromName` ます。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassm_nobjectsize"></a><a name="m_nobjectsize"></a> CRuntimeClass:: m_nObjectSize

オブジェクトのサイズ (バイト単位)。

### <a name="remarks"></a>解説

オブジェクトに割り当てられたメモリを指すデータメンバーがある場合、そのメモリのサイズは含まれません。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassm_pbaseclass"></a><a name="m_pbaseclass"></a> CRuntimeClass:: m_pBaseClass

アプリケーションが MFC と静的にリンクしている場合、このデータメンバーには `CRuntimeClass` 基底クラスの構造体へのポインターが含まれます。

### <a name="remarks"></a>解説

アプリケーションが MFC ライブラリに動的にリンクする場合は、「 [m_pfnGetBaseClass](#m_pfngetbaseclass)」を参照してください。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassm_pfncreateobject"></a><a name="m_pfncreateobject"></a> CRuntimeClass:: m_pfnCreateObject

クラスのオブジェクトを作成する既定のコンストラクターへの関数ポインター。

### <a name="remarks"></a>解説

このポインターは、クラスが動的作成をサポートしている場合にのみ有効です。それ以外の場合、関数は NULL を返します。

## <a name="cruntimeclassm_pfngetbaseclass"></a><a name="m_pfngetbaseclass"></a> CRuntimeClass:: m_pfnGetBaseClass

アプリケーションで MFC ライブラリを共有 DLL として使用する場合、このデータメンバーは、基本クラスの構造を返す関数を指し `CRuntimeClass` ます。

### <a name="remarks"></a>解説

アプリケーションが MFC ライブラリに静的にリンクしている場合は、「 [m_pBaseClass](#m_pbaseclass)」を参照してください。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

## <a name="cruntimeclassm_wschema"></a><a name="m_wschema"></a> CRuntimeClass:: m_wSchema

スキーマ番号 (シリアル化クラスの場合は-1)。

### <a name="remarks"></a>解説

スキーマ番号の詳細については、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) マクロを参照してください。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CObject:: GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
