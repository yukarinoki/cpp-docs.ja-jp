---
title: クラスを数える
ms.date: 11/04/2016
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
ms.openlocfilehash: 02b302ec38922128190a6f20ce2f156b52383b55
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752579"
---
# <a name="cmfccmdusagecount-class"></a>クラスを数える

ユーザーがメニューから項目を選択したときなど、Windows メッセージの使用回数を追跡します。

## <a name="syntax"></a>構文

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|既定のコンストラクターです。|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[をカウントします。](#addcmd)|指定されたコマンドに関連付けられているカウンターを 1 つ増やします。|
|[をカウントします。](#getcount)|指定されたコマンド ID に関連付けられている使用カウントを取得します。|
|[を使用します。](#hasenoughinformation)|このオブジェクトが最小追跡データを収集したかどうかを判断します。|
|[を使用します。](#isfreqeuntlyusedcmd)|指定したコマンドが頻繁に使用されるかどうかを判断します。|
|[をカウント::リセット](#reset)|すべてのコマンドの使用カウントをクリアします。|
|[を使用します。](#serialize)|このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|
|[を指定します。](#setoptions)|共有`CMFCCmdUsageCount`クラスのデータ メンバーの値を設定します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|名前|説明|
|`m_CmdUsage`|コマンド`CMap`をその使用カウントにマップするオブジェクト。|
|`m_nMinUsagePercentage`|頻繁に使用するコマンドの最小使用率。|
|`m_nStartCount`|このオブジェクトが最小追跡データを収集したかどうかを判断するために使用される開始カウンター。|
|`m_nTotalUsage`|追跡されたすべてのコマンドのカウント。|

### <a name="remarks"></a>解説

クラス`CMFCCmdUsageCount`は、各数値 Windows メッセージ識別子を 32 ビット符号なし整数カウンターにマップします。 `CMFCToolBar`このクラスを使用して、頻繁に使用されるツールバー項目を表示します。 の詳細`CMFCToolBar`については、「 [CMFC ツール バー クラス](../../mfc/reference/cmfctoolbar-class.md)」を参照してください。

プログラムの実行`CMFCCmdUsageCount`間にクラス データを保持できます。 クラス メンバー データをシリアル化するには[CMFCCmdUsageCount::Serialize](#serialize)メソッドを使用し、共有メンバー データを設定するメソッドを[使用](#setoptions)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[使用法のカウント](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmdusagecount.h

## <a name="cmfccmdusagecountaddcmd"></a><a name="addcmd"></a>をカウントします。

指定されたコマンドに関連付けられているカウンターを 1 つ増やします。

```cpp
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Uicmd*|[in]インクリメントするコマンド カウンターを指定します。|

### <a name="remarks"></a>解説

このメソッドは、エントリが存在しない場合は、`m_CmdUsage`コマンド カウントのマップ構造に新しいエントリを追加します。

このメソッドは、次の場合には何も行いません。

- ツール バー フレームワークはカスタマイズ モードです[(CMFCツールバー::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)メソッドは 0 以外の値を返します)。

- コマンドは、サブメニューまたはメニューの区切り記号を参照します *(uiCmd*は 0 または -1)。

- *uiCmd*は標準コマンドを参照します`IsStandardCommand`(グローバル関数は 0 以外の値を返します)。

## <a name="cmfccmdusagecountgetcount"></a><a name="getcount"></a>をカウントします。

指定されたコマンド ID に関連付けられている使用カウントを取得します。

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Uicmd*|[in]取得するコマンド カウンターの ID。|

### <a name="return-value"></a>戻り値

指定されたコマンド ID に関連付けられている使用カウント。

## <a name="cmfccmdusagecounthasenoughinformation"></a><a name="hasenoughinformation"></a>を使用します。

このオブジェクトが最小追跡データを受信したかどうかを判断します。

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトが最小追跡データを受け取った場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、追跡対象のコマンドの合計数が`m_nTotalUsage`初期カウント以上の場合は 0 以外の値を返`m_nStartCount`します。 既定では、フレームワークは初期カウント 0 を設定します。 この値をオーバーライドするには[、](#setoptions)メソッドを使用します。

このメソッドは、すべての使用可能なメニュー コマンドを表示するかどうかを決定するために[CMFCMenuBar::IsShowAll コマンド](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands)によって使用されます。

## <a name="cmfccmdusagecountisfreqeuntlyusedcmd"></a><a name="isfreqeuntlyusedcmd"></a>を使用します。

指定したコマンドが頻繁に使用されるかどうかを判断します。

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Uicmd*|[in]確認するコマンドを指定します。|

### <a name="return-value"></a>戻り値

コマンドが頻繁に使用される場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、コマンドの合計使用法が`m_nTotalUsage`0 の場合は 0 を返します。 それ以外の場合、指定したコマンドが使用される割合が最小パーセントより大きい場合、このメソッドは`m_nMinUsagePercentage`0 以外を返します。 既定では、フレームワークは最小のパーセンテージを 5 に設定します。 この値をオーバーライドするには[、](#setoptions)メソッドを使用します。 最小パーセンテージが 0 の場合、指定したコマンドカウントが 0 より大きい場合、このメソッドは 0 以外を返します。

[コマンドが](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused)ほとんど使用されないかどうかを判断するには、このメソッドを使用します。

## <a name="cmfccmdusagecountreset"></a><a name="reset"></a>をカウント::リセット

すべてのコマンドの使用カウントをクリアします。

```cpp
void Reset();
```

### <a name="remarks"></a>解説

コマンド カウントのマップ構造からすべてのエントリをクリアし、`m_CmdUsage`コマンドの合計使用をリセットするには、`m_nTotalUsage`このメソッドを呼び出します。

## <a name="cmfccmdusagecountserialize"></a><a name="serialize"></a>を使用します。

このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ar*|[in]シリアル`CArchive`化するオブジェクトまたはシリアル化するオブジェクト。|

### <a name="remarks"></a>解説

このメソッドは、コマンド カウントのマップ構造、`m_CmdUsage`およびコマンドの使用の合計`m_nTotalUsage`、、または指定したアーカイブに対するカウンターをシリアル化します。

シリアル化の例については、「[シリアル化: オブジェクトのシリアル化](../../mfc/serialization-serializing-an-object.md)」を参照してください。

## <a name="cmfccmdusagecountsetoptions"></a><a name="setoptions"></a>を指定します。

共有`CMFCCmdUsageCount`クラスのデータ メンバーの値を設定します。

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*カウント*|[in]すべての追跡対象コマンドの新しい初期カウント。|
|*nMin使用率の割合*|[in]新しい最小使用率。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE、*パラメーターが*100 以上の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、共有`CMFCCmdUsageCount`クラスのデータ`m_nStartCount``m_nMinUsagePercentage`メンバーと*nStartCount*と*nMinUsagePercentage*にそれぞれを設定します。 `m_nStartCount`は、このオブジェクトが追跡データの最小量を収集したかどうかを判断するために[、CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)メソッドによって使用されます。 `m_nMinUsagePercentage`は、特定のコマンドが頻繁に使用されているかどうかを判断するために[、CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)メソッドによって使用されます。

デバッグ ビルドでは、このメソッドは *、nMinUsagePercentage*パラメーターが 100 以上の場合にアサーション エラーを生成します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)
