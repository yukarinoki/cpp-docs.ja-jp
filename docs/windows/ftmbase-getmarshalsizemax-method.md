---
title: Ftmbase::getmarshalsizemax メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
dev_langs:
- C++
helpviewer_keywords:
- GetMarshalSizeMax method
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c39c313f06bb4dd1f4dbc095df159a38625e9db8
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570215"
---
# <a name="ftmbasegetmarshalsizemax-method"></a>FtmBase::GetMarshalSizeMax メソッド
指定したオブジェクトで指定されたインターフェイス ポインターをマーシャ リングするために必要なバイト数の上限を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
### <a name="parameters"></a>パラメーター  
 *riid*  
 マーシャ リングするインターフェイスの識別子への参照。  
  
 *現在価値*  
 インターフェイス ポインターをマーシャ リングします。NULL にすることができます。  
  
 *dwDestContext*  
 コピー先のコンテキストが指定されたインターフェイスのマーシャ リングできない位置。  
  
 1 つまたは複数の MSHCTX 列挙値を指定します。  
  
 現時点では、マーシャ リング解除発生する可能性が現在のプロセス (MSHCTX_INPROC) の別のアパートメントまたは現在のプロセス (MSHCTX_LOCAL) と同じコンピューター上の別のプロセスでします。  
  
 *pvDestContext*  
 今後使用するために予約されていますNULL にする必要があります。  
  
 *mshlflags*  
 マーシャ リングするデータがクライアント プロセスに送信されるかどうかを示すフラグ: 一般的なケース、または複数のクライアントで取得できる、グローバル テーブルに書き込まれます。 1 つまたは複数の MSHLFLAGS 列挙値を指定します。  
  
 *pSize*  
 この操作が完了時は、マーシャ リングのストリームに書き込まれるデータの量に上限へのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、または E_NOINTERFACE E_FAIL します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)