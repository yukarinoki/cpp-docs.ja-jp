---
description: 詳細については、「CMFCCmdUsageCount クラス」を参照してください。
title: CMFCCmdUsageCount クラス
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
ms.openlocfilehash: 40d09e96672cafb022baab98787fe10b1258048b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327722"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount クラス

ユーザーがメニューから項目を選択したときなど、Windows メッセージの使用状況を追跡します。

## <a name="syntax"></a>構文

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|-|-|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|既定のコンストラクターです。|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[CMFCCmdUsageCount:: AddCmd](#addcmd)|指定したコマンドに関連付けられているカウンターを1つずつインクリメントします。|
|[CMFCCmdUsageCount:: GetCount](#getcount)|指定したコマンド ID に関連付けられている使用状況カウントを取得します。|
|[CMFCCmdUsageCount:: HasEnoughInformation](#hasenoughinformation)|このオブジェクトによって追跡データの最小量が収集されたかどうかを判断します。|
|[CMFCCmdUsageCount:: Isfreqeunのコマンドレット](#isfreqeuntlyusedcmd)|指定されたコマンドが頻繁に使用されるかどうかを判断します。|
|[CMFCCmdUsageCount:: Reset](#reset)|すべてのコマンドの使用状況カウントをクリアします。|
|[CMFCCmdUsageCount:: Serialize](#serialize)|アーカイブからこのオブジェクトを読み取るか、アーカイブに書き込みます。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|
|[CMFCCmdUsageCount:: SetOptions](#setoptions)|共有クラスのデータメンバーの値を設定 `CMFCCmdUsageCount` します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|-|-|
|`m_CmdUsage`|`CMap`コマンドを使用量カウントにマップするオブジェクト。|
|`m_nMinUsagePercentage`|頻繁に使用されるコマンドの使用率の最小値です。|
|`m_nStartCount`|このオブジェクトによって追跡データの最小量が収集されたかどうかを判断するために使用される開始カウンター。|
|`m_nTotalUsage`|追跡されたすべてのコマンドの数。|

### <a name="remarks"></a>解説

クラスは、 `CMFCCmdUsageCount` 各数値 Windows メッセージ識別子を32ビット符号なし整数カウンターにマップします。 `CMFCToolBar` このクラスを使用して、頻繁に使用されるツールバー項目を表示します。 の詳細について `CMFCToolBar` は、「 [Cmfctoolbar クラス](../../mfc/reference/cmfctoolbar-class.md)」を参照してください。

`CMFCCmdUsageCount`プログラムの実行間でクラスデータを保持できます。 [Cmfccmdusagecount:: serialize](#serialize)メソッドを使用して、クラスメンバーデータをシリアル化し、 [Cmfccmdusagecount:: SetOptions](#setoptions)メソッドを使用して共有メンバーデータを設定します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxcmdusagecount

## <a name="cmfccmdusagecountaddcmd"></a><a name="addcmd"></a> CMFCCmdUsageCount:: AddCmd

指定したコマンドに関連付けられているカウンターを1つずつインクリメントします。

```cpp
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*uiCmd*\
からインクリメントするコマンドカウンターを指定します。

### <a name="remarks"></a>解説

このメソッドは、コマンド数のマップ構造に新しいエントリを追加し `m_CmdUsage` ます (エントリがまだ存在しない場合)。

このメソッドでは、次の場合に何も実行されません。

- ツールバーフレームワークはカスタマイズモードです ( [cmfctoolbar:: Iscustomization emode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) メソッドは0以外の値を返します)。

- このコマンドは、サブメニューまたはメニューの区切り記号 ( *uiCmd* equals 0 または-1) を参照します。

- *uiCmd* は標準コマンドを参照して `IsStandardCommand` います (グローバル関数は0以外の値を返します)。

## <a name="cmfccmdusagecountgetcount"></a><a name="getcount"></a> CMFCCmdUsageCount:: GetCount

指定したコマンド ID に関連付けられている使用状況カウントを取得します。

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>パラメーター

*uiCmd*\
から取得するコマンドカウンターの ID。

### <a name="return-value"></a>戻り値

指定したコマンド ID に関連付けられている使用状況カウント。

## <a name="cmfccmdusagecounthasenoughinformation"></a><a name="hasenoughinformation"></a> CMFCCmdUsageCount:: HasEnoughInformation

このオブジェクトが追跡データの最小量を受信したかどうかを判断します。

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>戻り値

このオブジェクトが最小の追跡データを受け取った場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメソッド `m_nTotalUsage` は、すべての追跡対象コマンドの合計数が、最初のカウント () 以上の場合に0以外の値を返し `m_nStartCount` ます。 既定では、フレームワークは初期カウント0を設定します。 この値は、 [Cmfccmdusagecount:: SetOptions](#setoptions) メソッドを使用してオーバーライドできます。

このメソッドは、使用可能なすべてのメニューコマンドを表示するかどうかを決定するために、 [Cmfcmenubar:: IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) によって使用されます。

## <a name="cmfccmdusagecountisfreqeuntlyusedcmd"></a><a name="isfreqeuntlyusedcmd"></a> CMFCCmdUsageCount:: Isfreqeunのコマンドレット

指定されたコマンドが頻繁に使用されるかどうかを判断します。

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>パラメーター

*uiCmd*\
から確認するコマンドを指定します。

### <a name="return-value"></a>戻り値

コマンドが頻繁に使用される場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

コマンドの合計使用量が0の場合、このメソッドは0を返し `m_nTotalUsage` ます。 それ以外の場合、このメソッドは、指定されたコマンドが使用されている割合が最小値 (%) よりも大きい場合、0以外の値を返し `m_nMinUsagePercentage` ます。 既定では、フレームワークによって最小の割合が5に設定されます。 この値は、 [Cmfccmdusagecount:: SetOptions](#setoptions) メソッドを使用してオーバーライドできます。 最小パーセンテージが0の場合、指定されたコマンド数が0より大きい場合、このメソッドは0以外の値を返します。

[Cmfctoolbar:: IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) は、このメソッドを使用して、コマンドがほとんど使用されないかどうかを判断します。

## <a name="cmfccmdusagecountreset"></a><a name="reset"></a> CMFCCmdUsageCount:: Reset

すべてのコマンドの使用状況カウントをクリアします。

```cpp
void Reset();
```

### <a name="remarks"></a>解説

このメソッドを呼び出して、コマンドカウント、、およびのすべてのエントリをクリアし、 `m_CmdUsage` コマンドの合計使用率を `m_nTotalUsage` 0 にリセットします。

## <a name="cmfccmdusagecountserialize"></a><a name="serialize"></a> CMFCCmdUsageCount:: Serialize

アーカイブからこのオブジェクトを読み取るか、アーカイブに書き込みます。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*金*\
から `CArchive` またはからシリアル化するオブジェクト。

### <a name="remarks"></a>解説

このメソッドは、コマンドカウントのマップ構造、 `m_CmdUsage` 、コマンドの合計使用量、 `m_nTotalUsage` 、または指定したアーカイブからのカウンターをシリアル化します。

シリアル化の例については、「 [シリアル化: オブジェクト](../../mfc/serialization-serializing-an-object.md)のシリアル化」を参照してください。

## <a name="cmfccmdusagecountsetoptions"></a><a name="setoptions"></a> CMFCCmdUsageCount:: SetOptions

共有クラスのデータメンバーの値を設定 `CMFCCmdUsageCount` します。

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>パラメーター

*nStartCount*\
からすべての追跡対象コマンドの新しい初期カウント。

*Nminの割合*\
から新しい最小使用率 (%)。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE、 *Nminの値* が100以上の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、共有 `CMFCCmdUsageCount` クラスのデータ `m_nStartCount` メンバー `m_nMinUsagePercentage` と *Nstartcount* と *nstartcount 割合* をそれぞれ設定します。 `m_nStartCount` は、 [Cmfccmdusagecount:: HasEnoughInformation](#hasenoughinformation) メソッドによって使用され、このオブジェクトによって追跡データの最小量が収集されたかどうかを判断します。 `m_nMinUsagePercentage` は、指定されたコマンドが頻繁に使用されるかどうかを判断するために、 [Cmfccmdusagecount:: Isfreqeunに](#isfreqeuntlyusedcmd) 使用される cmd メソッドによって使用されます。

デバッグビルドでは、 *Nminの値* が100以上の場合、このメソッドはアサーションエラーを生成します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)
