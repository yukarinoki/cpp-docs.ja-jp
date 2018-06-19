---
title: MFC クラス オブジェクトのキャストの型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 217be53a78a65a0f617438127b922b20c950853d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371162"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC クラス オブジェクトの型キャスト
型キャストのマクロは、指定されたポインター、キャストは有効なことを確認せず、特定のクラスのオブジェクトを指すポインターをキャストする方法を提供します。  
  
 次の表は、MFC 型のキャスト マクロを一覧表示します。  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC クラス オブジェクトへのポインターにキャストするマクロ  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|キャストが有効かどうかを確認中に、クラス オブジェクトへのポインターへのポインターをキャストします。|  
|[STATIC_DOWNCAST](#static_downcast)|関連する型のポインターに 1 つのクラスからオブジェクトへのポインターをキャストします。 デバッグ ビルドにより、 **ASSERT**オブジェクトがない場合、ターゲットの種類「の種類」です。|  
  
##  <a name="dynamic_downcast"></a>  DYNAMIC_DOWNCAST  
 キャストが有効かどうかを確認中に、クラスのオブジェクトへのポインターへのポインターをキャストする便利な方法を提供します。  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>パラメーター  
 `class`  
 クラスの名前。  
  
 `pointer`  
 型のオブジェクトへのポインターにキャストできるポインター`class`です。  
  
### <a name="remarks"></a>コメント  
 マクロはキャスト、`pointer`パラメーターのオブジェクトへのポインターを`class`パラメーターの型。  
  
 ポインターによって参照されるオブジェクトがある場合、識別されたクラス「の種類」マクロは、適切なポインターを返します。 マクロを返しますのかどうかはそうでない有効なキャスト**NULL**です。  
  
##  <a name="static_downcast"></a>  STATIC_DOWNCAST  
 キャスト*pobject*へのポインター、 *class_name*オブジェクト。  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 キャストされているクラスの名前。  
  
 *pobject*  
 ポインターにキャストするへのポインター、 *class_name*オブジェクト。  
  
### <a name="remarks"></a>コメント  
 *pobject*どちらかでなければなりません**NULL**、直接、派生クラスからまたは間接的に、オブジェクトを指すまたは*class_name*です。 使用してアプリケーションのビルドでは、 **_DEBUG**プリプロセッサ シンボルが定義されている、マクロは**ASSERT**場合*pobject*は**NULL**、またははないオブジェクトを指している場合で指定されたクラス「の種類」、 *class_name*パラメーター (を参照してください[使うため](../../mfc/reference/cobject-class.md#iskindof))。 以外の **_DEBUG**ビルド、マクロは、型チェックなしのキャストを実行します。  
  
 指定されたクラス、 *class_name*からパラメーターを派生する必要があります`CObject`および使用する必要があります、`DECLARE_DYNAMIC`と`IMPLEMENT_DYNAMIC`、`DECLARE_DYNCREATE`と`IMPLEMENT_DYNCREATE`、または`DECLARE_SERIAL`と`IMPLEMENT_SERIAL`マクロ、アーティクルの説明に従って[CObject クラス: CObject からクラスを派生する](../../mfc/deriving-a-class-from-cobject.md)です。  
  
 たとえばへのポインターをキャストする場合があります`CMyDoc`と呼ばれる、`pMyDoc`へのポインターに**CDocument**この式を使用します。  
  
 [!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 場合`pMyDoc`から直接または間接的に派生したオブジェクトを指していない**CDocument**、マクロは**ASSERT**です。  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
