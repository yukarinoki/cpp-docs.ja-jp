---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
ms.openlocfilehash: ebab34433f23b119e3444b3eaa8b0ad6313555af
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352365"
---
# <a name="ccacheddatapathproperty-class"></a>クラス

非同期で転送し、メモリ ファイルにキャッシュする OLE コントロール プロパティを実装します。

## <a name="syntax"></a>構文

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティを指定します。](#ccacheddatapathproperty)|`CCachedDataPathProperty` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[プロパティ::m_Cache](#m_cache)|`CMemFile`データをキャッシュするオブジェクト。|

## <a name="remarks"></a>解説

メモリ ファイルはディスクではなく RAM に格納され、高速な一時転送に役立ちます。

と共`CAysncMonikerFile`に`CDataPathProperty`、 `CCachedDataPathProperty` OLE コントロールで非同期モニカーを使用するための機能を提供します。 オブジェクト`CCachedDataPathProperty`を使用すると、URL またはファイル ソースから非同期にデータを転送し、パブリック変数を使用してメモリ`m_Cache`ファイルに格納できます。 すべてのデータはメモリ ファイルに格納され、通知を監視して応答する必要がない限り[、OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)をオーバーライドする必要はありません。 たとえば、大きな .GIFファイルと、より多くのデータが到着したことをコントロールに通知し、それが自分自身を再描画`OnDataAvailable`する必要があり、通知を行うためにオーバーライドします。

クラス`CCachedDataPathProperty`は`CDataPathProperty`から派生します。

インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次のトピックを参照してください。

- [インターネットの最初の手順: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)

- [インターネットの最初のステップ: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a>プロパティを指定します。

`CCachedDataPathProperty` オブジェクトを構築します。

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
この`CCachedDataPathProperty`オブジェクトに関連付ける ActiveX コントロール オブジェクトへのポインター。

*パス*<br/>
絶対パスまたは相対パスは、プロパティの実際の絶対位置を参照する非同期モニカーを作成するために使用されます。 `CCachedDataPathProperty`では、ファイル名ではなく URL を使用します。 ファイルのオブジェクトが`CCachedDataPathProperty`必要な場合は、パスの前にfile://します。

### <a name="remarks"></a>解説

`COleControl` *pControl*によって指されるオブジェクトは[、Open](../../mfc/reference/cdatapathproperty-class.md#open)によって使用され、派生クラスによって取得されます。 *pControl*が NULL の場合、`Open`使用するコントロールは[SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)で設定する必要があります。 *lpszPath*が NULL の場合は、パスを`Open`渡すか[、SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)を使用してパスを設定できます。

## <a name="ccacheddatapathpropertym_cache"></a><a name="m_cache"></a>プロパティ::m_Cache

データがキャッシュされるメモリ ファイルのクラス名を格納します。

```
CMemFile m_Cache;
```

### <a name="remarks"></a>解説

メモリ ファイルはディスクではなく RAM に格納されます。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cdatapathproperty-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdatapathproperty-class.md)
