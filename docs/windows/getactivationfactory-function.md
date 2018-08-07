---
title: GetActivationFactory 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2cbb5be3603f79a7df1cb330ca06775357666854
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570312"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory 関数
テンプレート パラメーターで指定された型のアクティベーション ファクトリを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 アクティベーション ファクトリの種類を指定するテンプレート パラメーター。  
  
 *activatableClassId*  
 アクティベーション ファクトリを作成できるクラスの名前。  
  
 *ファクトリ*  
 ときにこの操作が完了すると、型のアクティベーション ファクトリへの参照を*T*します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、この操作が失敗した理由を示す HRESULT エラー。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** windows::foundation  
  
## <a name="see-also"></a>関連項目  
 [Windows::Foundation 名前空間](../windows/windows-foundation-namespace.md)