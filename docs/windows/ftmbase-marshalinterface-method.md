---
title: Ftmbase::marshalinterface メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ff0c1a5e41dfe46f2d88aeeb3093dbc9ee4d4005
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570058"
---
# <a name="ftmbasemarshalinterface-method"></a>FtmBase::MarshalInterface メソッド
一部のクライアント プロセスで、プロキシ オブジェクトを初期化するために必要なデータをストリームに書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pStm*  
 マーシャ リング中に使用するストリームへのポインター。  
  
 *riid*  
 マーシャ リングするインターフェイスの識別子への参照。 このインターフェイスから派生する必要があります、`IUnknown`インターフェイス。  
  
 *現在価値*  
 マーシャ リング; へのインターフェイス ポインターへのポインター呼び出し元では、必要なインターフェイスには、ポインターにいない場合、NULL を指定できます。  
  
 *dwDestContext*  
 コピー先のコンテキストが指定されたインターフェイスのマーシャ リングできない位置。  
  
 1 つまたは複数の MSHCTX 列挙値を指定します。  
  
 マーシャ リング解除は、現在のプロセス (MSHCTX_INPROC) の別のアパートメントまたは (MSHCTX_LOCAL) の現在のプロセスと同じコンピューター上の別のプロセスでが発生することができます。  
  
 *pvDestContext*  
 今後使用するために予約されています。0 にする必要があります。  
  
 *mshlflags*  
 マーシャ リングするデータがクライアント プロセスに送信されるかどうかを指定します: 一般的なケース、または複数のクライアントで取得できる、グローバル テーブルに書き込まれます。  
  
## <a name="return-value"></a>戻り値  
 S_OK  
 インターフェイス ポインターが正常にマーシャ リングされます。  
  
 E_NOINTERFACE  
 指定したインターフェイスがサポートされていません。  
  
 STG_E_MEDIUMFULL  
 ストリームがいっぱいです。  
  
 E_FAIL  
 操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)