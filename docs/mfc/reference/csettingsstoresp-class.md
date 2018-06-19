---
title: CSettingsStoreSP クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1852f4e280fa49a2436c421d4669e9d735d66c3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376052"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP クラス
`CSettingsStoreSP`クラスは、ヘルパー クラスのインスタンスの作成に使用できる、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|`CSettingsStoreSP` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|派生したクラスのインスタンスを作成`CSettingsStore`です。|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|ランタイム クラスを設定します。 `Create`メソッドはランタイム クラスを使用して作成するオブジェクトのクラスを決定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`m_dwUserData`|カスタム ユーザー データに格納されている、`CSettingsStoreSP`オブジェクト。 コンス トラクターでは、このデータを指定する、`CSettingsStoreSP`オブジェクト。|  
|`m_pRegistry`|`CSettingsStore`-派生オブジェクトを`Create`メソッドを作成します。|  
  
## <a name="remarks"></a>コメント  
 使用することができます、`CSettingsStoreSP`すべての MFC レジストリ操作を XML ファイルやデータベースなど、他の場所にリダイレクトするクラス。 その場合は、次の手順を実行します。  
  
1.  クラスの作成 (など`CMyStore`) から派生`CSettingsStore`です。  
  
2.  使用して[DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)と[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)マクロとカスタム`CSettingsStore`動的生成を有効にするクラス。  
  
3.  仮想関数をオーバーライドおよび実装、`Read`と`Write`カスタム クラスに機能します。 目的の場所にデータを読み書きするその他の機能を実装します。  
  
4.  アプリケーションで呼び出す`CSettingsStoreSP::SetRuntimeClass`へのポインターに渡すと、 [CRuntimeClass 構造](../../mfc/reference/cruntimeclass-structure.md)クラスから取得します。  
  
 フレームワークは通常、レジストリにアクセスをするたびは動的にカスタム クラスをインスタンス化され読み取りまたは書き込みデータを使用します。  
  
 `CSettingsStoreSP::SetRuntimeClass` グローバルな静的変数を使用します。 したがって、1 つだけのカスタム ストアは、一度に使用します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsettingsstore.h  
  
##  <a name="create"></a>  CSettingsStoreSP::Create  
 派生したオブジェクトの新しいインスタンスを作成、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)です。  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAdmin`  
 決定するブール型のパラメーターかどうか、`CSettingsStore`管理者モードでオブジェクトを作成します。  
  
 [入力] `bReadOnly`  
 決定するブール型のパラメーターかどうか、`CSettingsStore`読み取り専用アクセスのオブジェクトを作成します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたへの参照を`CSettingsStore`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 メソッドを使用して[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)オブジェクトの種類を決定する`CSettingsStoreSP::Create`が作成されます。 既定では、このメソッドを作成、`CSettingsStore`オブジェクト。  
  
 作成する場合、`CSettingsStore`管理者モードでオブジェクトのすべてのレジストリへのアクセスの既定の場所は HKEY_LOCAL_MACHINE です。 それ以外の場合、既定の場所すべてのレジストリへのアクセスは、HKEY_CURRENT_USER です。  
  
 場合`bAdmin`は`TRUE`アプリケーションに管理権限が必要です。 それ以外の場合、レジストリにアクセスしようとするときに失敗します。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`Create`のメソッド、`CSettingsStoreSP`クラスです。  
  
 [!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="csettingsstoresp"></a>  CSettingsStoreSP::CSettingsStoreSP  
 構築、 [CSettingsStoreSP クラス](../../mfc/reference/csettingsstoresp-class.md)オブジェクト。  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwUserData`  
 ユーザー定義データを`CSettingsStoreSP`オブジェクトのストア。  
  
### <a name="remarks"></a>コメント  
 `CSettingsStoreSP`オブジェクトからデータを格納する`dwUserData`プロテクト メンバー変数に`m_dwUserData`です。  
  
##  <a name="setruntimeclass"></a>  CSettingsStoreSP::SetRuntimeClass  
 ランタイム クラスを設定します。 メソッド[CSettingsStoreSP::Create](#create)ランタイム クラスを使用して作成するオブジェクトの種類を決定します。  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRTI`  
 派生したクラスのランタイム クラス情報へのポインター、 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 成功した場合`FALSE`によってクラスが識別される場合`pRTI`から派生していない`CSettingsStore`です。  
  
### <a name="remarks"></a>コメント  
 使用することができます、 [CSettingsStoreSP クラス](../../mfc/reference/csettingsstoresp-class.md)からクラスを派生させる`CSettingsStore`です。 メソッドを使用して`SetRuntimeClass`から派生したカスタム クラスのオブジェクトを作成するかどうかは`CSettingsStore`します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)
