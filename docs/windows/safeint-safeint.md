---
title: Safeint::safeint |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d6bcac8dec2e85f0ea7d1d4530ed6ff1b7acc08
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604344"
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt
構築、 **SafeInt**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*しました*  
 新しい値**SafeInt**オブジェクト。 これには、コンス トラクターによって、型 T または U のパラメーターがあります。  
  
 [in]*b*  
 新しいブール値**SafeInt**オブジェクト。  
  
 [in]*u*  
 A **SafeInt**型 U の新しい**SafeInt**オブジェクトと同じ値になります*u*T 型になりますが、  
  
 U  
 格納されたデータの種類、 **SafeInt**します。 ブール値、文字、または整数のいずれかの型を指定できます。 整数型の場合は、符号付きまたは符号なし 8 と 64 ビットの間であるとします。  
  
## <a name="remarks"></a>Remarks  
 テンプレートの種類の詳細については`T`と`E`を参照してください[SafeInt クラス](../windows/safeint-class.md)します。  
  
 入力パラメーターをコンス トラクター、*は*または*u*、ブール値、文字、または整数型でなければなりません。 パラメーターの型を別の場合は、 **SafeInt**クラスが呼び出す[static_assert](../cpp/static-assert.md)を無効な入力パラメーターを示します。  
  
 テンプレートの種類を使用するコンス トラクター`U`自動的に入力パラメーターで指定された型に変換できる`T`します。 **SafeInt**クラスのデータを失うことがなくデータを変換します。 エラー ハンドラーに報告`E`、データ型に変換できない場合`T`データ損失なし。  
  
 作成する場合、 **SafeInt**ブール型のパラメーターから値をすぐに初期化する必要があります。 構築することはできません、 **SafeInt**コードを使用して`SafeInt<bool> sb;`します。 これにより、コンパイル エラーが生成されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeIntException クラス](../windows/safeintexception-class.md)