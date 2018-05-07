---
title: CMFCCmdUsageCount クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5b4824632d7ce38e50859172a24a47bdeb49f1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount クラス
など、ユーザーがメニューから項目を選択すると、Windows メッセージの使用率カウントを追跡します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|既定のコンストラクター|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|指定されたコマンドに関連付けられているカウンターを 1 つずつインクリメントされます。|  
|[CMFCCmdUsageCount::GetCount](#getcount)|指定されたコマンド ID に関連付けられている使用率カウントを取得します|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|このオブジェクトが追跡データの最小量を収集するかどうかを判断します。|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|指定されたコマンドが頻繁に使用するかどうかを判断します。|  
|[CMFCCmdUsageCount::Reset](#reset)|すべてのコマンドの使用率カウントをクリアします。|  
|[CMFCCmdUsageCount::Serialize](#serialize)|アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|セットの値は共有`CMFCCmdUsageCount`クラスのデータ メンバーです。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`m_CmdUsage`|A`CMap`コマンドを使用状況カウントをマップするオブジェクト。|  
|`m_nMinUsagePercentage`|頻繁に使用するコマンドの最小使用率。|  
|`m_nStartCount`|このオブジェクトが追跡データの最小量を収集するかどうかを決定するために使用開始カウンターです。|  
|`m_nTotalUsage`|追跡されているすべてのコマンド数。|  
  
### <a name="remarks"></a>コメント  
 `CMFCCmdUsageCount`クラスは、32 ビット符号なし整数のカウンターに各数値の Windows メッセージ識別子をマップします。 `CMFCToolBar` 頻繁に使用するツールバー項目を表示するのにには、このクラスを使用します。 詳細については`CMFCToolBar`を参照してください[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)です。  
  
 永続化できる`CMFCCmdUsageCount`プログラムの実行の間のデータのクラスです。 使用して、 [CMFCCmdUsageCount::Serialize](#serialize)クラス メンバー データをシリアル化するメソッドと[CMFCCmdUsageCount::SetOptions](#setoptions)共有メンバー データを設定します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmdusagecount.h  
  
##  <a name="addcmd"></a>  CMFCCmdUsageCount::AddCmd  
 指定されたコマンドに関連付けられているカウンターを 1 つずつインクリメントされます。  
  
```  
void AddCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `uiCmd`|インクリメントするコマンドのカウンターを指定します。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コマンドの数のマップの構造に新しいエントリを追加`m_CmdUsage`エントリが既に存在しない場合、します。  
  
 このメソッドでは、次の場合ではありません。  
  
-   カスタマイズ モードでは、ツールバーのフレームワーク (、 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)メソッドは 0 以外の値を返します)。  
  
-   コマンドはサブメニューまたはメニュー区分線を指します ( `uiCmd` equals 0 または-1)。  
  
- `uiCmd` 標準のコマンドを表します (グローバル`IsStandardCommand`関数は 0 以外の値を返します)。  
  
##  <a name="getcount"></a>  CMFCCmdUsageCount::GetCount  
 指定されたコマンド ID に関連付けられている使用率カウントを取得します  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `uiCmd`|取得するコマンドのカウンターの ID。|  
  
### <a name="return-value"></a>戻り値  
 指定されたコマンド ID に関連付けられている使用率カウント  
  
##  <a name="hasenoughinformation"></a>  CMFCCmdUsageCount::HasEnoughInformation  
 このオブジェクトが追跡データの最小量を受信したかどうかを判断します。  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外のオブジェクトが追跡データの最小量を受信しましたそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、場合に 0 以外の値を返します、総数、 `m_nTotalUsage`、追跡されているすべてのコマンドは最初の数以上`m_nStartCount`です。 既定では、フレームワークは、0 の最初の数を設定します。 使用してこの値をオーバーライドすることができます、 [CMFCCmdUsageCount::SetOptions](#setoptions)メソッドです。  
  
 このメソッドを使用して[CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands)を利用可能なメニュー コマンドをすべて表示するかどうかを判断します。  
  
##  <a name="isfreqeuntlyusedcmd"></a>  CMFCCmdUsageCount::IsFreqeuntlyUsedCmd  
 指定されたコマンドが頻繁に使用するかどうかを判断します。  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `uiCmd`|確認するコマンドを指定します。|  
  
### <a name="return-value"></a>戻り値  
 コマンドは、頻繁に使用される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、場合に 0 を返します合計コマンドの使用法、`m_nTotalUsage`は 0。 それ以外の場合、このメソッドは、指定されたコマンドを使用する割合は、割合の最小値よりも大きい場合は 0 以外を返します`m_nMinUsagePercentage`です。 既定では、フレームワークは、5 を割合の最小値を設定します。 使用してこの値をオーバーライドすることができます、 [CMFCCmdUsageCount::SetOptions](#setoptions)メソッドです。 割合の最小値が 0 の場合は、このメソッドは、指定されたコマンド数が 0 より大きい場合は 0 以外を返します。  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused)このメソッドを使用して、コマンドはほとんど使用されているかどうかを判断します。  
  
##  <a name="reset"></a>  CMFCCmdUsageCount::Reset  
 すべてのコマンドの使用率カウントをクリアします。  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>コメント  
 コマンドの数のマップの構造からすべてのエントリをクリアするには、このメソッドを呼び出す`m_CmdUsage`、および合計のコマンドの使用法をリセットするため`m_nTotalUsage`、カウンターを 0 にします。  
  
##  <a name="serialize"></a>  CMFCCmdUsageCount::Serialize  
 アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `ar`|A`CArchive`からまたはにシリアル化するオブジェクト。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コマンドの数のマップの構造をシリアル化`m_CmdUsage`、および合計コマンドの使用法、 `m_nTotalUsage`、または指定したアーカイブするカウンター。  
  
 シリアル化の例については、次を参照してください。[シリアル化: オブジェクトのシリアル化](../../mfc/serialization-serializing-an-object.md)です。  
  
##  <a name="setoptions"></a>  CMFCCmdUsageCount::SetOptions  
 セットの値は共有`CMFCCmdUsageCount`クラスのデータ メンバーです。  
  
```  
static BOOL __stdcall SetOptions(
    UINT nStartCount,  
    UINT nMinUsagePercentage);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `nStartCount`|新しい初期追跡されているすべてのコマンド数。|  
|[入力] `nMinUsagePercentage`|新しいの最小使用率。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功すると、`FALSE`場合、`nMinUsagePercentage`パラメーターがより大きいか、または 100 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、共有設定`CMFCCmdUsageCount`クラスのデータ メンバー`m_nStartCount`と`m_nMinUsagePercentage`に`nStartCount`と`nMinUsagePercentage`、それぞれします。 `m_nStartCount` によって使用される、 [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)メソッドをこのオブジェクトが追跡データの最小量を収集するかどうかを決定します。 `m_nMinUsagePercentage` によって使用される、 [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)指定されたコマンドが頻繁に使用するかどうかを調べます。  
  
 場合はデバッグ ビルドでこのメソッドが、アサーションの失敗を生成、`nMinUsagePercentage`パラメーターがより大きいか、または 100 です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)
