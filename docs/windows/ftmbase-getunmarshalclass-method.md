---
title: Ftmbase::getunmarshalclass メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs:
- C++
helpviewer_keywords:
- GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 329d43227aa131728db72086f99cb86797a5e1e3
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571153"
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass メソッド
COM を使用して、対応するプロキシのコードを含む DLL を検索する CLSID を取得します。 COM は初期化されていないプロキシのインスタンスを作成するには、この DLL を読み込みます。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
### <a name="parameters"></a>パラメーター  
 *riid*  
 マーシャ リングするインターフェイスの識別子への参照。  
  
 *現在価値*  
 マーシャ リングする; インターフェイスへのポインター呼び出し元では、必要なインターフェイスには、ポインターにいない場合、NULL を指定できます。  
  
 *dwDestContext*  
 コピー先のコンテキストが指定されたインターフェイスのマーシャ リングできない位置。  
  
 1 つまたは複数の MSHCTX 列挙値を指定します。  
  
 マーシャ リング解除は、現在のプロセス (MSHCTX_INPROC) の別のアパートメントまたは現在のプロセス (MSHCTX_LOCAL) と同じコンピューター上の別のプロセスで発生します。  
  
 *pvDestContext*  
 今後使用するために予約されていますNULL にする必要があります。  
  
 *mshlflags*  
 この操作が完了時は、クライアント プロセスで、プロキシの作成に使用する、CLSID へのポインター。  
  
 *pCid*  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、s_false を返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)