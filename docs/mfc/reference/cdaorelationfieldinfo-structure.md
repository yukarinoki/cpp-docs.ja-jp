---
description: '詳細については、次を参照してください: CDaoRelationFieldInfo 構造体'
title: CDaoRelationFieldInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: eb470752a9e9da5f610dd59976f2716fa1c4e18a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248165"
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo 構造体

構造体には、 `CDaoRelationFieldInfo` データアクセスオブジェクト (DAO) に対して定義されているリレーションシップ内のフィールドに関する情報が含まれています。

## <a name="syntax"></a>構文

```
struct CDaoRelationFieldInfo
{
    CString m_strName;           // Primary
    CString m_strForeignName;    // Primary
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
リレーションシップの主テーブル内のフィールドの名前。

*m_strForeignName*<br/>
リレーションシップの外部テーブル内のフィールドの名前。

## <a name="remarks"></a>解説

DAO リレーションシップオブジェクトでは、主テーブルのフィールドと、リレーションシップを定義する外部テーブルのフィールドを指定します。 上の構造体定義の Primary への参照は、 `m_pFieldInfos` クラスの[GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)メンバー関数を呼び出すことによって取得される[CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)オブジェクトのメンバーで情報がどのように返されるかを示して `CDaoDatabase` います。

リレーションシップオブジェクトとリレーションシップフィールドオブジェクトは、MFC クラスでは表されません。 代わりに、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) クラスの基になる DAO オブジェクトには、リレーションコレクションと呼ばれる relation オブジェクトのコレクションが含まれています。 各リレーションシップオブジェクトには、リレーションシップフィールドオブジェクトのコレクションが含まれています。 各リレーションシップフィールドオブジェクトは、主テーブルのフィールドを外部テーブルのフィールドと関連付けます。 リレーションシップフィールドオブジェクトでは、各テーブルのフィールドのグループを定義して、リレーションシップを定義します。 `CDaoDatabase``CDaoRelationInfo`メンバー関数を呼び出すことによって、オブジェクトを使用してリレーションシップオブジェクトにアクセスできるように `GetRelationInfo` します。 `CDaoRelationInfo`オブジェクトには、 `m_pFieldInfos` オブジェクトの配列を指すデータメンバーがあり `CDaoRelationFieldInfo` ます。

対象のリレーションシップオブジェクトが格納されている内の、親オブジェクトの [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) メンバー関数を呼び出し `CDaoDatabase` ます。 次に、 `m_pFieldInfos` [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) オブジェクトのメンバーにアクセスします。 `CDaoRelationFieldInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoRelationFieldInfo` ます。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoRelationInfo 構造体](../../mfc/reference/cdaorelationinfo-structure.md)
