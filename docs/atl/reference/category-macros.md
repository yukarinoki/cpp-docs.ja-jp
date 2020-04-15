---
title: カテゴリ マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CATEGORY_MAP
- atlcom/ATL::END_CATEGORY_MAP
- atlcom/ATL::IMPLEMENTED_CATEGORY
- atlcom/ATL::REQUIRED_CATEGORY
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
ms.openlocfilehash: 1d8bbae4608aa661bbc612604f7d85855f325f5f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321595"
---
# <a name="category-macros"></a>カテゴリ マクロ

これらのマクロは、カテゴリ マップを定義します。

|||
|-|-|
|[BEGIN_CATEGORY_MAP](#begin_category_map)|カテゴリ マップの先頭を示します。|
|[END_CATEGORY_MAP](#end_category_map)|カテゴリ マップの末尾をマークします。|
|[IMPLEMENTED_CATEGORY](#implemented_category)|COM オブジェクトによって実装されるカテゴリを示します。|
|[REQUIRED_CATEGORY](#required_category)|COM オブジェクトによってコンテナに必要なカテゴリを示します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="begin_category_map"></a><a name="begin_category_map"></a>BEGIN_CATEGORY_MAP

カテゴリ マップの先頭を示します。

```
BEGIN_CATEGORY_MAP(theClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
[in]カテゴリ マップを含むクラスの名前。

### <a name="remarks"></a>解説

カテゴリ マップは、COM クラスが実装するコンポーネント カテゴリと、そのコンテナから必要なカテゴリを指定するために使用されます。

COM クラスによって実装される各カテゴリのマップに[IMPLEMENTED_CATEGORY](#implemented_category)エントリを追加します。 クラスが実装する必要がある各カテゴリの[REQUIRED_CATEGORY](#required_category)エントリをマップに追加します。 END_CATEGORY_MAP[マクロで](#end_category_map)マップの終わりをマークします。

クラスに関連付けられた[OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto)または[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)がある場合、マップにリストされているコンポーネント カテゴリは、モジュールが登録されたときに自動的に登録されます。

> [!NOTE]
> ATL は、標準コンポーネント カテゴリ マネージャを使用して、コンポーネント カテゴリを登録します。 モジュールの登録時にマネージャがシステムに存在しない場合、登録は成功しますが、コンポーネントカテゴリはそのクラスに登録されません。

コンポーネント カテゴリの詳細については、「[コンポーネント カテゴリとは」と](/windows/win32/com/component-categories-and-how-they-work)「Windows SDK でのコンポーネント カテゴリの動作」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="end_category_map"></a><a name="end_category_map"></a>END_CATEGORY_MAP

カテゴリ マップの末尾をマークします。

```
END_CATEGORY_MAP()
```

### <a name="example"></a>例

[BEGIN_CATEGORY_MAP](#begin_category_map)の例を参照してください。

## <a name="implemented_category"></a><a name="implemented_category"></a>IMPLEMENTED_CATEGORY

IMPLEMENTED_CATEGORY マクロをコンポーネントの[カテゴリ マップ](#begin_category_map)に追加して *、catID*パラメーターで識別されるカテゴリを実装するように登録するように指定します。

```
IMPLEMENTED_CATEGORY(catID)
```

### <a name="parameters"></a>パラメーター

*Catid*<br/>
[in]実装されたカテゴリのグローバル一意識別子 (GUID) を保持する CATID 定数または変数。 *catID*のアドレスが取得され、マップに追加されます。 在庫カテゴリの選択については、以下の表を参照してください。

### <a name="remarks"></a>解説

クラスに関連付けられた[OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto)またはマクロがある場合、マップにリストされているコンポーネント カテゴリは、モジュールが登録されるときに自動的に登録[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO。](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)

クライアントは、クラスに登録されたカテゴリ情報を使用して、そのクラスのインスタンスを作成することなく、その機能と要件を決定できます。

コンポーネント カテゴリの詳細については、「[コンポーネント カテゴリとは」と](/windows/win32/com/component-categories-and-how-they-work)「Windows SDK でのコンポーネント カテゴリの動作」を参照してください。

### <a name="a-selection-of-stock-categories"></a>株式カテゴリの選択

|説明|Symbol|レジストリ GUID|
|-----------------|------------|-------------------|
|スクリプト用に安全|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|初期化に安全|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|シンプル フレーム サイトコンテインメント|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|単純データ バインディング|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|高度なデータ バインディング|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|ウィンドウなしのコントロール|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|インターネットに対応するオブジェクト|サンプル リストについては、Windows SDK の[インターネット対応オブジェクト](/windows/win32/com/internet-aware-objects)を参照してください。||

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="required_category"></a><a name="required_category"></a>REQUIRED_CATEGORY

コンポーネントの[カテゴリ マップ](#begin_category_map)にREQUIRED_CATEGORY マクロを追加して *、catID*パラメーターで識別されるカテゴリが必要な場合に登録するように指定します。

```
REQUIRED_CATEGORY( catID )
```

### <a name="parameters"></a>パラメーター

*Catid*<br/>
[in]必要なカテゴリのグローバル一意識別子 (GUID) を保持する CATID 定数または変数。 *catID*のアドレスが取得され、マップに追加されます。 在庫カテゴリの選択については、以下の表を参照してください。

### <a name="remarks"></a>解説

クラスに関連付けられた[OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto)またはマクロがある場合、マップにリストされているコンポーネント カテゴリは、モジュールが登録されるときに自動的に登録[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO。](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)

クライアントは、クラスに登録されたカテゴリ情報を使用して、そのクラスのインスタンスを作成することなく、その機能と要件を決定できます。 たとえば、コントロールでは、コンテナーがデータ バインディングをサポートする必要があります。 コンテナーは、そのコントロールに必要なカテゴリマネージャーを照会することで、コントロールをホストするために必要な機能を持っているかどうかを確認できます。 コンテナが必要な機能をサポートしていない場合、COM オブジェクトのホストを拒否できます。

サンプル リストを含むコンポーネント カテゴリの詳細については、「[コンポーネント カテゴリとは」と](/windows/win32/com/component-categories-and-how-they-work)「Windows SDK でのコンポーネント カテゴリの動作」を参照してください。

### <a name="a-selection-of-stock-categories"></a>株式カテゴリの選択

|説明|Symbol|レジストリ GUID|
|-----------------|------------|-------------------|
|スクリプト用に安全|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|初期化に安全|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|シンプル フレーム サイトコンテインメント|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|単純データ バインディング|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|高度なデータ バインディング|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|ウィンドウなしのコントロール|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|インターネットに対応するオブジェクト|サンプル リストについては、Windows SDK の[インターネット対応オブジェクト](/windows/win32/com/internet-aware-objects)を参照してください。||

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
