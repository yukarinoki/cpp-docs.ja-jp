---
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
ms.openlocfilehash: 92979a10c18d9759e0ecc9f0785e56a97c0f0642
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426787"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass 構造体

`CObject` から派生した各クラスは、実行時にオブジェクトまたはその基本クラスに関する情報を取得するために使用できる `CRuntimeClass` 構造に関連付けられています。

## <a name="syntax"></a>構文

```
struct CRuntimeClass
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CRuntimeClass:: CreateObject](#createobject)|実行時にオブジェクトを作成します。|
|[CRuntimeClass:: FromName](#fromname)|使い慣れたクラス名を使用して、実行時にオブジェクトを作成します。|
|[CRuntimeClass:: IsDerivedFrom](#isderivedfrom)|指定したクラスから派生したクラスかどうかを判断します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|Description|
|----------|-----------------|
|[CRuntimeClass:: m_lpszClassName](#m_lpszclassname)|クラスの名前。|
|[CRuntimeClass:: m_nObjectSize](#m_nobjectsize)|オブジェクトのサイズ (バイト単位)。|
|[CRuntimeClass:: m_pBaseClass](#m_pbaseclass)|基底クラスの `CRuntimeClass` 構造体へのポインター。|
|[CRuntimeClass:: m_pfnCreateObject](#m_pfncreateobject)|オブジェクトを動的に作成する関数へのポインター。|
|[CRuntimeClass:: m_pfnGetBaseClass](#m_pfngetbaseclass)|`CRuntimeClass` 構造体を返します (動的にリンクされている場合にのみ使用できます)。|
|[CRuntimeClass:: m_wSchema](#m_wschema)|クラスのスキーマ番号。|

## <a name="remarks"></a>解説

`CRuntimeClass` は構造体であるため、基本クラスはありません。

実行時にオブジェクトのクラスを決定する機能は、関数の引数の追加の型チェックが必要な場合、またはオブジェクトのクラスに基づいて特殊な目的のコードを記述する必要がある場合に便利です。 ランタイムクラス情報は、 C++言語によって直接サポートされていません。

`CRuntimeClass` は、関連するC++オブジェクトに関する情報を提供します。たとえば、基底クラスの `CRuntimeClass` へのポインターや、関連するクラスの ASCII クラス名へのポインターなどです。 この構造体には、オブジェクトを動的に作成したり、使い慣れた名前を使用してオブジェクトの型を指定したり、関連するクラスが特定のクラスから派生したかどうかを判断したりするために使用できるさまざまな関数も実装されています。

`CRuntimeClass`の使用方法の詳細については、「[ランタイムクラス情報へのアクセス](../../mfc/accessing-run-time-class-information.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CRuntimeClass`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

##  <a name="createobject"></a>CRuntimeClass:: CreateObject

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

`CObject` から派生したクラスは動的作成をサポートできます。これは、実行時に指定したクラスのオブジェクトを作成する機能です。 たとえば、ドキュメント、ビュー、およびフレームクラスでは、動的作成がサポートされている必要があります。 動的作成と `CreateObject` メンバーの詳細については、「 [Cobject クラス](../../mfc/using-cobject.md)と[Cobject クラス: 機能のレベルの指定](../../mfc/specifying-levels-of-functionality.md)」を参照してください。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

##  <a name="fromname"></a>CRuntimeClass:: FromName

この関数を呼び出して、使い慣れた名前に関連付けられている `CRuntimeClass` 構造体を取得します。

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>パラメーター

*lpszClassName*<br/>
`CObject`から派生したクラスのわかりやすい名前。

### <a name="return-value"></a>戻り値

*Lpszclassname*に渡された名前に対応する `CRuntimeClass` オブジェクトへのポインター。 一致するクラス名が見つからなかった場合、関数は NULL を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

##  <a name="isderivedfrom"></a>CRuntimeClass:: IsDerivedFrom

この関数を呼び出して、 *pBaseClass*パラメーターで指定したクラスから呼び出し元のクラスが派生しているかどうかを確認します。

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>パラメーター

*pBaseClass*<br/>
`CObject`から派生したクラスのわかりやすい名前。

### <a name="return-value"></a>戻り値

`IsDerivedFrom` を呼び出すクラスが、`CRuntimeClass` 構造体がパラメーターとして指定されている基本クラスから派生している場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

リレーションシップは、メンバーのクラスの "ウォーキング" によって、最上位に至るまでの派生クラスのチェーンによって決定されます。 この関数は、基底クラスの一致が検出されない場合にのみ、FALSE を返します。

> [!NOTE]
>  `CRuntimeClass` 構造体を使用するには、実行時オブジェクト情報を取得するクラスの実装に、IMPLEMENT_DYNAMIC、IMPLEMENT_DYNCREATE、または IMPLEMENT_SERIAL マクロを含める必要があります。

`CRuntimeClass`の使用方法の詳細については、「 [CObject クラス: Run Time クラス情報へのアクセス](../../mfc/accessing-run-time-class-information.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

##  <a name="m_lpszclassname"></a>CRuntimeClass:: m_lpszClassName

ASCII クラス名を格納している null で終わる文字列。

### <a name="remarks"></a>解説

この名前は、`FromName` メンバー関数を使用してクラスのインスタンスを作成するために使用できます。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

##  <a name="m_nobjectsize"></a>CRuntimeClass:: m_nObjectSize

オブジェクトのサイズ (バイト単位)。

### <a name="remarks"></a>解説

オブジェクトに割り当てられたメモリを指すデータメンバーがある場合、そのメモリのサイズは含まれません。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

##  <a name="m_pbaseclass"></a>CRuntimeClass:: m_pBaseClass

アプリケーションが MFC と静的にリンクしている場合、このデータメンバーには、基底クラスの `CRuntimeClass` 構造へのポインターが含まれます。

### <a name="remarks"></a>解説

アプリケーションが MFC ライブラリに動的にリンクする場合は、「 [m_pfnGetBaseClass](#m_pfngetbaseclass)」を参照してください。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

##  <a name="m_pfncreateobject"></a>CRuntimeClass:: m_pfnCreateObject

クラスのオブジェクトを作成する既定のコンストラクターへの関数ポインター。

### <a name="remarks"></a>解説

このポインターは、クラスが動的作成をサポートしている場合にのみ有効です。それ以外の場合、関数は NULL を返します。

##  <a name="m_pfngetbaseclass"></a>CRuntimeClass:: m_pfnGetBaseClass

アプリケーションで MFC ライブラリを共有 DLL として使用する場合、このデータメンバーは、基底クラスの `CRuntimeClass` 構造を返す関数を指します。

### <a name="remarks"></a>解説

アプリケーションが MFC ライブラリに静的にリンクしている場合は、「 [m_pBaseClass](#m_pbaseclass)」を参照してください。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

##  <a name="m_wschema"></a>CRuntimeClass:: m_wSchema

スキーマ番号 (シリアル化クラスの場合は-1)。

### <a name="remarks"></a>解説

スキーマ番号の詳細については、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロを参照してください。

### <a name="example"></a>例

  [IsDerivedFrom](#isderivedfrom)の例を参照してください。

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CObject:: GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
