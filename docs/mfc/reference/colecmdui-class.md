---
title: COleCmdUI クラス
ms.date: 07/24/2020
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
ms.openlocfilehash: c21d9b504656e6bba5ca693e57958743bb1b8309
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233211"
---
# <a name="colecmdui-class"></a>COleCmdUI クラス

アプリケーションの `IOleCommandTarget`ドリブンの機能に関連するユーザー インターフェイス オブジェクトの状態を更新するメソッドを MFC に提供します。

## <a name="syntax"></a>構文

```cpp
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleCmdUI::COleCmdUI](#colecmdui)|`COleCmdUI` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleCmdUI:: Enable](#enable)|Enable コマンドフラグを設定または解除します。|
|[COleCmdUI::SetCheck](#setcheck)|オン/オフのトグルコマンドの状態を設定します。|
|[COleCmdUI:: SetText](#settext)|コマンドのテキスト名またはステータス文字列を返します。|

## <a name="remarks"></a>解説

DocObjects が有効になっていないアプリケーションでは、ユーザーがアプリケーションのメニューを表示すると、MFC は、通知を UPDATE_COMMAND_UI します。 各通知には、特定のコマンドの状態を反映するために操作できる[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトが付与されます。 ただし、アプリケーションが DocObjects に対して有効になっている場合、MFC は通知 UPDATE_OLE_COMMAND_UI 処理し、オブジェクトを割り当て `COleCmdUI` ます。

`COleCmdUI`DocObject が、コンテナーのユーザーインターフェイス (FileNew、Open、Print など) で発生したコマンドを受け取ることができるようにします。また、DocObject のユーザーインターフェイスで生成されたコマンドをコンテナーが受信できるようにします。 は `IDispatch` 、同じコマンドをディスパッチするために使用できますが、は、 `IOleCommandTarget` 標準のコマンドセット (通常は引数を含まない) に依存していて、型情報が関係していないため、より簡単なクエリおよび実行方法を提供します。 `COleCmdUI`DocObject user interface コマンドの他のプロパティを有効にしたり、更新したり、設定したりするために使用できます。 コマンドを起動する場合は、 [COleServerDoc:: OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)を呼び出します。

DocObjects の詳細については、「 [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) and [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CCmdUI](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdocob

## <a name="colecmduicolecmdui"></a><a name="colecmdui"></a>COleCmdUI::COleCmdUI

特定の `COleCmdUI` ユーザーインターフェイスコマンドに関連付けられたオブジェクトを構築します。

```cpp
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>パラメーター

*rgCmds*<br/>
指定した GUID に関連付けられている、サポートされているコマンドの一覧。 `OLECMD`構造体はコマンドをコマンドフラグに関連付けます。

*cCmds*<br/>
*RgCmds*内のコマンドの数。

*pGroup*<br/>
コマンドのセットを識別する GUID へのポインター。

### <a name="remarks"></a>解説

オブジェクトには、 `COleCmdUI` メニュー項目やコントロールバーボタンなどの DocObject ユーザーインターフェイスオブジェクトを更新するためのプログラムインターフェイスが用意されています。 オブジェクトを使用して、ユーザーインターフェイスオブジェクトを有効にしたり、無効にしたり、チェックしたり、クリアしたりでき `COleCmdUI` ます。

## <a name="colecmduienable"></a><a name="enable"></a>COleCmdUI:: Enable

この関数を呼び出して、オブジェクトのコマンドフラグを OLECOMDF_ENABLED に設定します。これにより `COleCmdUI` 、コマンドが使用可能で有効になっていることをインターフェイスに通知したり、コマンドフラグをクリアしたりできます。

```cpp
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>パラメーター

*楽しい*<br/>
オブジェクトに関連付けられたコマンドを有効にするか無効にするかを示し `COleCmdUI` ます。 0以外の場合、コマンドを有効にします。0の場合、コマンドは無効になります。

## <a name="colecmduisetcheck"></a><a name="setcheck"></a>COleCmdUI::SetCheck

この関数を呼び出して、on/off トグルコマンドの状態を設定します。

```cpp
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>パラメーター

*n*<br/>
オン/オフの切り替えコマンドを設定する状態を決定する値。 値は次のとおりです。

|値|[説明]|
|-----------|-----------------|
|**1**|コマンドを on に設定します。|
|**2**|コマンドを不確定に設定します。このコマンドの属性が関連する選択項目のオン状態とオフ状態の両方にあるため、状態を特定できません。|
|その他の値|コマンドを off に設定します。|

## <a name="colecmduisettext"></a><a name="settext"></a>COleCmdUI:: SetText

コマンドのテキスト名またはステータス文字列を返すには、この関数を呼び出します。

```cpp
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
コマンドで使用されるテキストへのポインター。

## <a name="see-also"></a>関連項目

[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
