---
description: '詳細情報: CCachedDataPathProperty クラス'
title: CCachedDataPathProperty クラス
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
ms.openlocfilehash: a61d2553afc4415da29399293843deb1be5f113d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122500"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty クラス

非同期で転送し、メモリ ファイルにキャッシュする OLE コントロール プロパティを実装します。

## <a name="syntax"></a>構文

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|`CCachedDataPathProperty` オブジェクトを構築します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CCachedDataPathProperty:: m_Cache](#m_cache)|`CMemFile` データをキャッシュするオブジェクト。|

## <a name="remarks"></a>解説

メモリファイルはディスク上ではなく RAM に格納され、高速な一時的な転送に便利です。

およびと共に `CAysncMonikerFile` `CDataPathProperty` 、 `CCachedDataPathProperty` OLE コントロールで非同期モニカーを使用するための機能を提供します。 オブジェクトを使用すると `CCachedDataPathProperty` 、URL またはファイルソースから非同期的にデータを転送し、パブリック変数を使用してメモリファイルに格納することができ `m_Cache` ます。 すべてのデータはメモリファイルに格納されます。通知を監視して応答する場合を除き、 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) を上書きする必要はありません。 たとえば、大きなを転送する場合です。GIF ファイルで、さらに多くのデータが到着し、それ自体を再描画する必要があることをコントロールに通知し、 `OnDataAvailable` 通知を行うためにオーバーライドします。

クラス `CCachedDataPathProperty` はから派生 `CDataPathProperty` しています。

インターネットアプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次のトピックを参照してください。

- [インターネットの最初の手順: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)

- [インターネットの最初の手順: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>要件

**ヘッダー:** afxctl.h

## <a name="ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a> CCachedDataPathProperty::CCachedDataPathProperty

`CCachedDataPathProperty` オブジェクトを構築します。

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>パラメーター

*pControl*<br/>
このオブジェクトに関連付けられる ActiveX コントロールオブジェクトへのポインター `CCachedDataPathProperty` 。

*lpszPath*<br/>
絶対パスまたは相対パスを指定します。このパスは、プロパティの実際の絶対位置を参照する非同期モニカーを作成するために使用されます。 `CCachedDataPathProperty` ファイル名ではなく Url を使用します。 ファイルのオブジェクトが必要な場合は `CCachedDataPathProperty` 、パスに file://を付加します。

### <a name="remarks"></a>解説

`COleControl` *Pcontrol* が指すオブジェクトは、[オープン](../../mfc/reference/cdatapathproperty-class.md#open)で、派生クラスによって取得されます。 *Pcontrol* が NULL の場合は、で使用されるコントロールを `Open` [setcontrol](../../mfc/reference/cdatapathproperty-class.md#setcontrol)で設定する必要があります。 *Lpszpath* が NULL の場合は、パスをから渡す `Open` か、 [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)で設定できます。

## <a name="ccacheddatapathpropertym_cache"></a><a name="m_cache"></a> CCachedDataPathProperty:: m_Cache

データがキャッシュされるメモリファイルのクラス名を格納します。

```
CMemFile m_Cache;
```

### <a name="remarks"></a>解説

メモリファイルは、ディスク上ではなく RAM に格納されます。

## <a name="see-also"></a>関連項目

[CDataPathProperty クラス](../../mfc/reference/cdatapathproperty-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDataPathProperty クラス](../../mfc/reference/cdatapathproperty-class.md)
