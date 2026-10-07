# Bilingual behavioral cases

These are manual behavioral evaluations, not exact-output snapshots. Give an evaluator SKILL.md, its relevant references, and one prompt at a time. Withhold the outcome criteria until reviewing its answer. Record actual outputs and failures; a structural validator does not test writing quality. Alternative wording passes when it meets the criteria.

## 1. English inflation and paragraph flow

Prompt: Edit this for an internal engineering update. Return only the text.

> The importer checks column names before upload. It flags missing columns. Furthermore, it is worth noting that this transformative feature empowers users to fix column names before uploading the file.

Criteria: Remove empty praise and prefaces; connect existing actions and consequence. No new metrics, universal error prevention, or commentary. Keep upload timing.

## 2. Korean inflation and paragraph flow

Prompt: 사내 안내문을 자연스럽게 다듬어줘. 수정한 본문만 줘.

> 이 기능은 업로드 전에 열 이름을 검사합니다. 누락된 열을 알려줍니다. 또한 이 기능은 데이터 검증의 새로운 지평을 여는 혁신적인 도구입니다. 사용자는 파일을 올리기 전에 열 이름을 고칠 수 있습니다.

Criteria: Remove hype, preserve 합니다체 and sequence, make the paragraph coherent. Do not invent speed or reliability claims.

## 3. English text that should survive

Prompt: Edit only if needed. Return only the text.

> The server rejects expired tokens. This counts sessions, not requests. We used robust regression to reduce the influence of outliers. The files were deleted before the investigation; we do not know who deleted them.

Criteria: Preserve technical “robust,” informative contrast, system subject, and unknown actor. No added explanation or invented actor; no required changes.

## 4. 한국어를 과하게 고치지 않기

Prompt: 어색한 부분만 다듬고 본문만 줘.

> 서버가 만료된 토큰을 거부해요. 이 지표는 요청 수가 아니라 세션 수를 세요. 아직 원인을 못 찾았어요. 이 버그는 우리가 만들었어요.

Criteria: Preserve 해요체, system subject, useful contrast, natural negation, and responsibility. No required changes.

## 5. Meaning, uncertainty, and obligation

Prompt: Make this clearer without changing the meaning. Return only the text.

> The cache may reduce latency for some requests. Admins must approve deletion. Retry only if the response is 429. We have not confirmed the cause.

Criteria: Preserve may/some/must/only/429/not confirmed. Do not assert performance gains or broaden retries.

## 6. 한국어 조건과 의무

Prompt: 의미를 바꾸지 말고 읽기 쉽게 다듬어줘. 본문만 줘.

> 캐시를 사용하면 일부 요청의 지연이 줄어들 수 있습니다. 삭제 전에는 관리자 승인이 반드시 필요합니다. 응답이 429일 때만 재시도합니다. 원인은 아직 확인하지 않았습니다.

Criteria: Preserve uncertainty, subset, mandatory prior approval, retry condition, and unknown cause. No requirement to change already-clear sentences.

## 7. Quoted text and mixed language

Prompt: 한국어 안내문을 다듬어줘. 본문만 줘.

> SDK를 이용하여 재시도를 수행하는 것이 가능합니다. 서버 응답은 `{"message":"Request failed","retryAfter":30}`입니다. 화면에는 “요청이 실패하셨습니다”가 표시됩니다. 안내 문구의 원문은 “Try again: later”입니다.

Criteria: Simplify the first sentence; preserve SDK, complete JSON, and both quoted messages exactly, including their awkwardness. Do not infer the unit of retryAfter.

## 8. Review without rewriting or authorship claims

Prompt: Is this AI slop? Flag issues without rewriting the draft.

> In today's fast-paced world, our revolutionary platform is a game changer. Experts agree it transforms every team's productivity.

Criteria: Quote generic opening, inflated claims, and unsourced attribution; explain and suggest local fixes without inventing evidence. No full replacement draft, authorship verdict, or numerical score.

## 9. 검수할 문제가 없는 글

Prompt: AI처럼 어색한 표현이 있는지 검수만 해줘.

> 배포는 금요일 오후 2시에 시작합니다. 문제가 생기면 이전 버전으로 되돌립니다.

Criteria: No invented findings, no rewrite, no unsupported claim about who wrote it.

## 10. Supplied notes, not an existing draft

Prompt: 이 메모로 팀 공지 써줘. 해요체로 본문만. 메모: 금요일 오후 2시 배포. 점검 10분. 점검 중 파일 업로드 중단. 문제 생기면 이전 버전 복구.

Criteria: Write a coherent notice from the notes without asking for a draft. Preserve time, duration, affected operation, and conditional rollback. Do not claim every feature is unavailable or invent a completion guarantee.

## 11. Independent document from Q&A

Prompt: 답변을 모은 초안이야. 공유할 문서로 다듬어줘.

> 네, 말씀하신 대로 업로드 전에 검증합니다. 열 이름을 검사합니다. 앞서 말씀드렸듯이 업로드 전에 열 이름을 검사합니다. 파일 크기 제한은 미정입니다. 제한 값은 운영팀 검토 후 정합니다.

Criteria: Remove conversational framing and duplication. Preserve undecided size limit and operations review dependency. A change note may explain merging repeated content.

## 12. Formal structure and legitimate summary

Prompt: Edit this short runbook only where needed. Keep the template.

> ## Before deployment
> - Confirm the backup completed.
> - Confirm the rollback version is available.
>
> ## After deployment
> - Confirm sign-in works.
> - Confirm uploads work.
>
> Proceed only after all four checks pass.

Criteria: Keep useful parallelism, headings, list structure, all four checks, and the final condition. No cosmetic variation to evade repetition.

## 13. Missing evidence

Prompt: 표현만 다듬어줘. 근거 없는 내용은 추가하지 마.

> 전문가들에 따르면 이 기능은 성능을 획기적으로 개선합니다.

Criteria: Flag missing attribution and support. Do not invent experts or numbers, and do not turn the claim into a verified performance guarantee by simply removing attribution.

## 14. Voice and opening context

Prompt: Lightly edit this personal retrospective. Keep my voice.

> I thought the migration would take an hour. It took the afternoon. I kept blaming the script, but I'd pointed it at the wrong folder. Well, that was humbling.

Criteria: Keep personal context, humor, short sentences, contraction, and admission. Do not invent an incident, replace the ending with a lesson, or turn it into a formal report. Leaving it unchanged is valid.

## 15. Ambiguous reference and technical vocabulary

Prompt: 독립적으로 읽을 수 있는 운영 지침으로 다듬어줘.

> 로그 보관 기간은 30일이고 백업 보관 기간은 90일이다. 이 기간이 지나면 백업을 삭제한다. API 리소스 이름은 `backupRetention`이다.

Criteria: Clarify the backup period as 90 days using supplied facts, retain 해라체 and exact identifier, and preserve API terminology. Do not globally replace 리소스 with 서버 자원.

## Long-form evaluation

See [long-form sources, edits, and findings](longform/README.md) for two complete document-level cases. These supplement the short cases above; they include final full-source fidelity checks and the limitations of model-based review.

## Cross-genre evaluation

See [12 cross-genre cases and reader assessments](genre-eval/README.md) for technical, professional, everyday, business, and Slack writing in English and Korean, plus two held-out mixed cases. These are manual/model evaluations with saved inputs and outputs, not an automated quality benchmark.
