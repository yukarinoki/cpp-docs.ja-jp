---
title: CMFCAcceleratorKey クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e04bcdf797f7036d943219f9d067dcbf786cfa3
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039782"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey クラス
仮想キーのマッピングおよび書式設定を実装するヘルパー クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|`CMFCAcceleratorKey` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|ACCEL 構造体のビジュアル表現に変換します。|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|ショートカット キーを設定、`CMFCAcceleratorKey`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 アクセラレータ キーは、ショートカット キーとも呼ばれます。 ユーザー入力すると、キーボード ショートカットを表示する場合、 [CMFCAcceleratorKeyAssignCtrl クラス](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)マップのショートカット キー、Alt + Shift + S など"Alt + Shift + S"などのカスタム テキスト形式にします。 各`CMFCAcceleratorKey`オブジェクトは、テキスト形式を 1 つのショートカット キーをマップします。  
  
 ショートカット キーとアクセラレータ テーブルを使用する方法の詳細については、次を参照してください。 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)です。  
  
## <a name="example"></a>例  
 次の例で作成する方法、`CMFCAcceleratorKey`オブジェクトと、使用する方法、`Format`メソッドです。  
  
 [!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey"></a>  CMFCAcceleratorKey::CMFCAcceleratorKey  
 構築、 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクト。  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpAccel*  
 ショートカット キーへのポインター。  
  
### <a name="remarks"></a>Remarks  
 作成するときは、ショートカット キーを指定しないかどうか、`CMFCAccleratorKey`を使用して、 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator)メソッドのショートカット キーを関連付けるには、`CMFCAcceleratorKey`オブジェクト。  
  
##  <a name="format"></a>  CMFCAcceleratorKey::Format  
 関連付けられている文字列値がそのアクセル構造を変換します。  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*str*  
 参照、`CString`メソッドが変換されたショートカット キーを書き込むオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、関連付けられているショートカット キーの文字列形式を取得します。 文字列形式を設定することができます、 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクト コンス トラクターまたはメソッドのいずれかを使用して[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)です。  
  
##  <a name="setaccelerator"></a>  CMFCAcceleratorKey::SetAccelerator  
 ショートカット キーを設定、 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクト。  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpAccel*  
 ショートカット キーへのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドのショートカット キーの設定を使用して、`CMFCAcceleratorKey`作成したときに、ショートカット キーを指定しなかったかどうか、`CMFCAcceleratorKey`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)
