---
title: Ftmbase::getunmarshalclass メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 09afd9f977dbc779eb1dc10e9553d2ca88538fcc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873304"
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass メソッド
COM を使用して、対応するプロキシ コードを含む DLL を検索する CLSID を取得します。 COM は、プロキシの初期化されていないインスタンスを作成するには、この DLL を読み込みます。  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 マーシャ リングするインターフェイスの識別子への参照。  
  
 `pv`  
 マーシャ リングする; インターフェイスへのポインター呼び出し元では、目的のインターフェイスには、ポインターにいない場合、NULL を指定できます。  
  
 `dwDestContext`  
 移行先コンテキストで指定されたインターフェイスのマーシャ リングします。  
  
 1 つまたは複数の MSHCTX 列挙値を指定します。  
  
 マーシャ リング解除 (MSHCTX_INPROC) 現在のプロセスの別のアパートメントまたは現在のプロセス (MSHCTX_LOCAL) と同じコンピューター上の別のプロセスで発生します。  
  
 `pvDestContext`  
 将来使用するために予約されていますNULL にする必要があります。  
  
 `mshlflags`  
 この操作の完了時、クライアント プロセスでプロキシを作成するために使用する CLSID へのポインター。  
  
 `pCid`  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合は S_FALSE。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)