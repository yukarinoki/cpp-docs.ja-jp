---
title: クラス
ms.date: 10/18/2018
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
ms.openlocfilehash: f41937179dc055213f3af093e107bcb08c8a8fcc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369961"
---
# <a name="cmenutearoffmanager-class"></a>クラス

ティアオフ メニューを管理します。 ティアオフ メニューはメニュー バー上のメニューの一種です。 ユーザーは、ティアオフ メニューをメニュー バーから外して、フローティング メニューにすることができます。

   詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[メニューティアオフマネージャー::CMenuティアオフマネージャー](#cmenutearoffmanager)|`CMenuTearOffManager` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[メニューティアオフマネージャー::ビルド](#build)||
|[メニューティアオフマネージャー::ゲットレグパス](#getregpath)||
|[メニューティアオフマネージャー::初期化](#initialize)|オブジェクトを`CMenuTearOffManager`初期化します。|
|[メニューティアオフマネージャー::イスダイナミックイド](#isdynamicid)||
|[メニューティアオフマネージャー::P](#parse)||
|[メニューティアオフマネージャー::リセット](#reset)||
|[メニューティアオフマネージャー::セットインユース](#setinuse)||
|[メニューティアオフマネージャー::セットアップティアオフメニュー](#setuptearoffmenus)||

## <a name="remarks"></a>解説

アプリケーションでティアオフ メニューを使用するには、オブジェクトが必要です`CMenuTearOffManager`。 ほとんどの場合、`CMenuTearOffManager`オブジェクトを直接作成または初期化することはありません。 これは[、CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)関数を呼び出すときに処理されます。

## <a name="example"></a>例

メソッドを呼び出してオブジェクトを構築および初期化`CMenuTearOffManager`する方法を次`CWinAppEX::EnableTearOffMenus`の例に示します。 このコード スニペットは、 [Word パッド サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmenuティアオフマネージャー.h

## <a name="cmenutearoffmanagerbuild"></a><a name="build"></a>メニューティアオフマネージャー::ビルド

```
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>パラメーター

[in]*uiティアオフバーID*<br/>

[in]*str テキスト*<br/>

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a>メニューティアオフマネージャー::CMenuティアオフマネージャー

[オブジェクトを](../../mfc/reference/cmenutearoffmanager-class.md)構築します。

```
CMenuTearOffManager();
```

### <a name="remarks"></a>解説

ほとんどの場合、手動で`CMenuTearOffManager`作成しないでください。 アプリケーションのフレームワークは`CMenuTearOffManager`[、CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)を呼び出すとオブジェクトを作成します。

## <a name="cmenutearoffmanagergetregpath"></a><a name="getregpath"></a>メニューティアオフマネージャー::ゲットレグパス

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagerinitialize"></a><a name="initialize"></a>メニューティアオフマネージャー::初期化

[オブジェクトを](../../mfc/reference/cmenutearoffmanager-class.md)初期化します。

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]レジストリ エントリのパスを含む文字列。 アプリケーションは、このレジストリ エントリにティアオフ バーの設定を格納します。

*最初にメニューを表示します。*<br/>
[in]ティアオフ メニューの最初のメニュー ID。

*uiティアオフメニューラスト*<br/>
[in]ティアオフ メニューの最後のメニュー ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

メニュー ID の範囲は *、最初から uiTearOffMenuLast*まで連続間隔でなければなりません。 *uiTearOffMenuLast* 間隔は、アプリケーションで同時に表示できるティアオフ メニューの数を定義します。

## <a name="cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a>メニューティアオフマネージャー::イスダイナミックイド

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>パラメーター

[in]*UIID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagerparse"></a><a name="parse"></a>メニューティアオフマネージャー::P

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>パラメーター

[in]*str*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagerreset"></a><a name="reset"></a>メニューティアオフマネージャー::リセット

```
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>パラメーター

[in]*hmenu*<br/>

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagersetinuse"></a><a name="setinuse"></a>メニューティアオフマネージャー::セットインユース

```
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*uiCmdId*<br/>

[in]*bUse*<br/>

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a>メニューティアオフマネージャー::セットアップティアオフメニュー

```
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

[in]*hメニュー*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
