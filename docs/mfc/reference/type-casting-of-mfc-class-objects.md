---
title: MFC クラス オブジェクトの型キャスト
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: 953acc32c3510b31c265f2d64d0a013f6dee06cc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372889"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC クラス オブジェクトの型キャスト

型キャスト マクロは、特定のクラスのオブジェクトを指すポインターへのポインターを、キャストが有効であることを確認する場合と、または無効にする方法を提供します。

次の表は、MFC 型キャスト マクロの一覧です。

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC クラス オブジェクトへのポインターをキャストするマクロ

|||
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|キャストが有効かどうかをチェックしながら、クラス オブジェクトへのポインターへのポインターをキャストします。|
|[STATIC_DOWNCAST](#static_downcast)|1 つのクラスから関連する型のポインターへのポインターをキャストします。 デバッグ ビルドでは、オブジェクトがターゲット型の "種類" でない場合に ASSERT が発生します。|

## <a name="dynamic_downcast"></a><a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST

キャストが有効かどうかを確認しながら、クラス オブジェクトへのポインターへのポインターをキャストする便利な方法を提供します。

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>パラメーター

*class*<br/>
クラスの名前。

*ポインター (pointer)*<br/>
*class*型のオブジェクトへのポインターにキャストするポインター。

### <a name="remarks"></a>解説

マクロは、*クラス*パラメーターの型のオブジェクトへのポインターに*ポインター*パラメーターをキャストします。

ポインターによって参照されるオブジェクトが、識別されたクラスの種類である場合、マクロは適切なポインターを返します。 有効なキャストでない場合、マクロは NULL を返します。

## <a name="static_downcast"></a><a name="static_downcast"></a>STATIC_DOWNCAST

*pobject*を*class_name*オブジェクトへのポインターにキャストします。

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
キャストされるクラスの名前。

*pオブジェクト*<br/>
*class_name*オブジェクトへのポインターにキャストするポインター。

### <a name="remarks"></a>解説

*pobject*は NULL であるか、直接または間接に派生したクラスのオブジェクトを指*class_name。* _DEBUGプリプロセッサシンボルが定義されたアプリケーションのビルドでは *、pobject*が NULL でない場合、または*class_name*パラメータで指定されたクラスの種類ではないオブジェクトを指している場合、マクロは ASSERT を実行します[(CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)を参照)。 **_DEBUG以外**のビルドでは、マクロは型チェックを行わずにキャストを実行します。

*class_name*パラメータで指定するクラスは、DECLARE_DYNAMICと`CObject`IMPLEMENT_DYNAMIC、DECLARE_DYNCREATEとIMPLEMENT_DYNCREATE、または[記事 CObject クラス: CObject からクラスを派生する](../../mfc/deriving-a-class-from-cobject.md)」で説明されているDECLARE_SERIALとIMPLEMENT_SERIALマクロから派生し、使用する必要があります。

たとえば、 にポインターを`CMyDoc`キャストすると、 という`pMyDoc`名前のポインターが、`CDocument`次の式を使用するポインターにキャストできます。

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

から`pMyDoc`直接または間接的`CDocument`に派生したオブジェクトを指していない場合、マクロは ASSERT を実行します。

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
