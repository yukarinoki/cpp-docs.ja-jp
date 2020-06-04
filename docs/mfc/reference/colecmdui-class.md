---
title: クラス
ms.date: 09/12/2018
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
ms.openlocfilehash: 1b7a6b21a3ad778b4a5ca345b1aaf42875810e4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376264"
---
# <a name="colecmdui-class"></a>クラス

アプリケーションの `IOleCommandTarget`ドリブンの機能に関連するユーザー インターフェイス オブジェクトの状態を更新するメソッドを MFC に提供します。

## <a name="syntax"></a>構文

```
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次のコマンドを実行します。](#colecmdui)|`COleCmdUI` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を有効にします。](#enable)|enable コマンド フラグを設定またはクリアします。|
|[をクリックします。](#setcheck)|オン/オフトグル コマンドの状態を設定します。|
|[をクリックします。](#settext)|コマンドのテキスト名またはステータス文字列を返します。|

## <a name="remarks"></a>解説

DocObjects が有効になっていないアプリケーションでは、ユーザーがアプリケーションのメニューを表示すると、MFC はUPDATE_COMMAND_UIの処理を行います。 各通知には、特定のコマンドの状態を反映するように操作できる[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトが与えられます。 ただし、アプリケーションで DocObjects が有効になっている場合、MFC は通知UPDATE_OLE_COMMAND_UI処理`COleCmdUI`し、オブジェクトを割り当てます。

`COleCmdUI`を使用すると、コンテナのユーザインタフェース(FileNew、Open、Printなど)から発信されたコマンドを DocObject が受け取ることができ、コンテナは DocObject のユーザインタフェースから生成されたコマンドを受け取ることができます。 同`IDispatch`じコマンドをディスパッチするために使用できますが、`IOleCommandTarget`通常は引数を持たない標準のコマンド セットに依存しており、型情報は含まないため、クエリと実行を簡単に行えます。 `COleCmdUI`を使用して、DocObject ユーザー インターフェイス コマンドのその他のプロパティを有効、更新、および設定できます。 コマンドを呼び出す場合は、[呼](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)び出します。

ドキュトオブジェクトの詳細については、[を](../../mfc/reference/cdocobjectserver-class.md)参照[してください。](../../mfc/reference/cdocobjectserveritem-class.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CCmdUI](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdocobj.h

## <a name="colecmduicolecmdui"></a><a name="colecmdui"></a>次のコマンドを実行します。

特定のユーザー`COleCmdUI`インターフェイス コマンドに関連付けられたオブジェクトを構築します。

```
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>パラメーター

*rgCmds*<br/>
指定された GUID に関連付けられているサポートされているコマンドの一覧。 この`OLECMD`構造体は、コマンドをコマンド・フラグに関連付けます。

*cCmds*<br/>
*rgCmds*内のコマンドの数。

*グループ化*<br/>
コマンドのセットを識別する GUID へのポインター。

### <a name="remarks"></a>解説

この`COleCmdUI`オブジェクトは、メニュー項目やコントロール バー ボタンなどの DocObject ユーザー インターフェイス オブジェクトを更新するためのプログラム インターフェイスを提供します。 ユーザー インターフェイス オブジェクトは、`COleCmdUI`オブジェクトを介して有効、無効、チェック、およびクリアできます。

## <a name="colecmduienable"></a><a name="enable"></a>を有効にします。

この関数を呼び出して、`COleCmdUI`オブジェクトのコマンド フラグをOLECOMDF_ENABLEDに設定します。

```
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>パラメーター

*ボン*<br/>
オブジェクトに関連付けられたコマンドを`COleCmdUI`有効にするか無効にするかを示します。 0 以外のコマンドは有効です。0 を指定すると、コマンドは無効になります。

## <a name="colecmduisetcheck"></a><a name="setcheck"></a>をクリックします。

オン/オフトグル コマンドの状態を設定します。

```
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>パラメーター

*nチェック*<br/>
オン/オフトグル コマンドを設定する状態を決定する値。 値は次のとおりです。

|[値]|説明|
|-----------|-----------------|
|**1**|コマンドを on に設定します。|
|**2**|コマンドを不確定に設定します。このコマンドの属性は、関連する選択のオンとオフの両方の状態にあるため、状態を特定できません。|
|その他の値|コマンドを off に設定します。|

## <a name="colecmduisettext"></a><a name="settext"></a>をクリックします。

コマンドのテキスト名またはステータス文字列を返します。

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
コマンドで使用されるテキストへのポインター。

## <a name="see-also"></a>関連項目

[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
