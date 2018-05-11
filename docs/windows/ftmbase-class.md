---
title: FtmBase クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
dev_langs:
- C++
helpviewer_keywords:
- FtmBase class
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7bcc003811a747569f22f6b2603faf72096dd049
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ftmbase-class"></a>FtmBase クラス
フリー スレッド マーシャラー オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,   
   Microsoft::WRL::CloakedIid<IMarshal> >;  
```  
  
## <a name="remarks"></a>コメント  
 詳細については、MSDN ライブラリの「COM リファレンス」トピックの"COM インターフェイス"サブトピック「"IMarshal"トピックを参照してください。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[FtmBase::FtmBase コンストラクター](../windows/ftmbase-ftmbase-constructor.md)|FtmBase クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[FtmBase::CreateGlobalInterfaceTable メソッド](../windows/ftmbase-createglobalinterfacetable-method.md)|グローバル インターフェイス テーブル (GIT) を作成します。|  
|[FtmBase::DisconnectObject メソッド](../windows/ftmbase-disconnectobject-method.md)|オブジェクトへのすべての外部接続を強制的に解放します。 オブジェクトのサーバーでは、シャット ダウンする前にこのメソッドのオブジェクトの実装を呼び出します。|  
|[FtmBase::GetMarshalSizeMax メソッド](../windows/ftmbase-getmarshalsizemax-method.md)|指定したオブジェクトの指定されたインターフェイス ポインターをマーシャ リングするために必要なバイト数の上限値を取得します。|  
|[FtmBase::GetUnmarshalClass メソッド](../windows/ftmbase-getunmarshalclass-method.md)|COM を使用して、対応するプロキシ コードを含む DLL を検索する CLSID を取得します。 COM は、プロキシの初期化されていないインスタンスを作成するには、この DLL を読み込みます。|  
|[FtmBase::MarshalInterface メソッド](../windows/ftmbase-marshalinterface-method.md)|一部のクライアント プロセスで、プロキシ オブジェクトを初期化するために必要なデータをストリームに書き込みます。|  
|[FtmBase::ReleaseMarshalData メソッド](../windows/ftmbase-releasemarshaldata-method.md)|マーシャ リング データ パケットを破棄します。|  
|[FtmBase::UnmarshalInterface メソッド](../windows/ftmbase-unmarshalinterface-method.md)|新しく作成されたプロキシを初期化し、そのプロキシにインターフェイス ポインターを返します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[FtmBase::marshaller_ データ メンバー](../windows/ftmbase-marshaller-data-member.md)|フリー スレッド マーシャラーへの参照を保持します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `FtmBase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)