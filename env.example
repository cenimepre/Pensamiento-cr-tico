const profileName = document.querySelector("#profileName");
const situationInput = document.querySelector("#situationInput");
const beforeInput = document.querySelector("#beforeInput");
const thoughtInput = document.querySelector("#thoughtInput");
const evidenceInput = document.querySelector("#evidenceInput");
const emotionSelect = document.querySelector("#emotionSelect");
const supportModeSelect = document.querySelector("#supportModeSelect");
const responseToneSelect = document.querySelector("#responseToneSelect");
const intensityRange = document.querySelector("#intensityRange");
const intensityValue = document.querySelector("#intensityValue");
const sendBtn = document.querySelector("#sendBtn");
const exampleBtn = document.querySelector("#exampleBtn");
const chatOutput = document.querySelector("#chatOutput");
const aiStatus = document.querySelector("#aiStatus");
const patternsPanel = document.querySelector("#patternsPanel");
const historyList = document.querySelector("#historyList");
const clearHistoryBtn = document.querySelector("#clearHistoryBtn");
const refreshPatternsBtn = document.querySelector("#refreshPatternsBtn");
const simpleSummaryPanel = document.querySelector("#simpleSummaryPanel");
const refreshSummaryBtn = document.querySelector("#refreshSummaryBtn");
const feelingsMessages = document.querySelector("#feelingsMessages");
const feelingsInput = document.querySelector("#feelingsInput");
const sendFeelingsBtn = document.querySelector("#sendFeelingsBtn");
const clearFeelingsChatBtn = document.querySelector("#clearFeelingsChatBtn");
const historyTemplate = document.querySelector("#historyItemTemplate");

const STOPWORDS = new Set([
  "que", "porque", "para", "pero", "como", "con", "sin", "una", "uno", "unos", "unas",
  "del", "las", "los", "por", "estoy", "estaba", "esta", "este", "esto", "eso", "esa",
  "ese", "me", "mi", "mis", "se", "de", "la", "el", "y", "o", "a", "en", "un", "al",
  "lo", "no", "creo", "pienso", "siento", "seguro", "capaz", "muy", "mas", "más",
  "tengo", "tenía", "tenia", "hacer", "hice", "pasó", "paso", "antes", "después",
  "despues", "ahora", "algo", "todo", "nada", "solo", "sólo", "ser", "estar", "voy",
  "van", "había", "habia", "cuando", "donde", "dónde", "cual", "cuál", "quien", "quién",
  "venía", "venia", "vino", "iba", "estaba", "estaban", "estuve", "estuviera", "estuviese",
  "apareció", "aparecio", "aparece", "aparecer", "pasa", "pasar", "pensamiento", "persona",
  "situación", "situacion", "evidencia", "emoción", "emocion", "principal", "registro"
]);

const DISTORTIONS = [
  {
    id: "catastrofizacion",
    label: "catastrofización",
    description: "La mente salta al peor escenario posible.",
    words: [
      "terrible", "desastre", "peor", "arruine", "arruiné", "despedir", "echar",
      "nunca voy", "todo va a salir mal", "se va a arruinar", "voy a perder"
    ]
  },
  {
    id: "lectura_mente",
    label: "lectura de mente",
    description: "La mente cree saber qué piensa otra persona sin tener pruebas suficientes.",
    words: [
      "piensa que", "cree que", "seguro piensa", "seguro cree", "me odia",
      "está enojado", "esta enojado", "está molesto", "esta molesto", "le caigo mal"
    ]
  },
  {
    id: "adivinacion_futuro",
    label: "adivinación del futuro",
    description: "La mente trata una predicción como si fuera un hecho confirmado.",
    words: [
      "va a", "me van a", "seguro va", "voy a perder", "me va a despedir",
      "va a salir mal", "no voy a poder", "me va a ir mal"
    ]
  },
  {
    id: "todo_o_nada",
    label: "pensamiento todo o nada",
    description: "La mente interpreta la situación en extremos: perfecto o desastre.",
    words: [
      "siempre", "nunca", "todo", "nada", "nadie", "todos", "soy un desastre",
      "no sirvo", "fracaso total"
    ]
  },
  {
    id: "filtro_negativo",
    label: "filtro negativo",
    description: "La mente se queda solo con lo negativo e ignora datos más equilibrados.",
    words: [
      "solo salió mal", "solo salio mal", "todo salió mal", "todo salio mal",
      "nada bueno", "lo bueno no importa", "lo único que importa", "lo unico que importa",
      "solo veo lo malo"
    ]
  },
  {
    id: "descalificar_positivo",
    label: "descalificar lo positivo",
    description: "La mente le quita valor a lo que salió bien.",
    words: [
      "no cuenta", "fue suerte", "fue de suerte", "fue casualidad", "fue de casualidad",
      "cualquiera pudo", "no fue para tanto", "no vale", "solo tuve suerte"
    ]
  },
  {
    id: "culpa_excesiva",
    label: "culpa excesiva",
    description: "La mente toma demasiada responsabilidad, incluso cuando hay otros factores.",
    words: [
      "todo es mi culpa", "culpa", "soy culpable", "por mi culpa", "por mí culpa",
      "fue por mi", "fue por mí", "arruiné todo", "arruine todo"
    ]
  },
  {
    id: "razonamiento_emocional",
    label: "razonamiento emocional",
    description: "La mente toma lo que siente como si fuera una prueba.",
    words: [
      "siento que", "me siento", "lo siento real", "se siente real",
      "si lo siento es porque", "tengo la sensación", "tengo la sensacion",
      "me da la sensación", "me da la sensacion"
    ]
  }
];

const CRISIS_PATTERNS = [
  "me quiero morir",
  "quiero morirme",
  "quiero morir",
  "quiero matarme",
  "voy a matarme",
  "me voy a matar",
  "quiero suicidarme",
  "voy a suicidarme",
  "me quiero suicidar",
  "quiero hacerme daño",
  "voy a hacerme daño",
  "me voy a hacer daño",
  "quiero lastimarme",
  "voy a lastimarme",
  "no quiero vivir",
  "quiero dejar de vivir",
  "quiero desaparecer",
  "quiero hacerle daño",
  "voy a hacerle daño",
  "quiero matar a",
  "voy a matar a"
];

const CRISIS_NEGATION_PATTERNS = [
  "no me quiero morir",
  "no quiero morirme",
  "no quiero morir",
  "no quiero matarme",
  "no voy a matarme",
  "no me voy a matar",
  "no quiero suicidarme",
  "no voy a suicidarme",
  "no me quiero suicidar",
  "no quiero hacerme daño",
  "no voy a hacerme daño",
  "no me voy a hacer daño",
  "no quiero lastimarme",
  "no voy a lastimarme",
  "no quiero atentar contra mi vida",
  "no queria atentar contra mi vida",
  "no quería atentar contra mi vida",
  "no voy a atentar contra mi vida",
  "no tengo intencion de hacerme daño",
  "no tengo intención de hacerme daño",
  "no tengo ideas suicidas",
  "no quiero hacerle daño",
  "no voy a hacerle daño",
  "no quiero matar a",
  "no voy a matar a"
];

profileName.value = localStorage.getItem("pc_profile_name") || "";

intensityRange.addEventListener("input", () => {
  intensityValue.textContent = intensityRange.value;
});

profileName.addEventListener("input", () => {
  localStorage.setItem("pc_profile_name", profileName.value.trim());
  renderHistory();
  renderPatterns();
  renderSimpleSummary();
});

refreshPatternsBtn.addEventListener("click", () => {
  renderPatterns();
  renderSimpleSummary();
});

refreshSummaryBtn.addEventListener("click", renderSimpleSummary);

sendFeelingsBtn.addEventListener("click", sendFeelingsMessage);

feelingsInput.addEventListener("keydown", (event) => {
  if (event.key === "Enter" && !event.shiftKey) {
    event.preventDefault();
    sendFeelingsMessage();
  }
});

clearFeelingsChatBtn.addEventListener("click", () => {
  const ok = confirm("¿Borrar esta conversación?");
  if (!ok) return;
  localStorage.removeItem(feelingsKey());
  renderFeelingsConversation();
});

exampleBtn.addEventListener("click", () => {
  situationInput.value = "Tiré un bidón de aceite en el trabajo.";
  beforeInput.value = "Venía apurada, estaba nerviosa y mi jefe ya estaba bastante serio.";
  thoughtInput.value = "Mi jefe me va a despedir porque cometí ese error.";
  evidenceInput.value = "No me dijo que me iba a despedir. Solo siento miedo y todavía no respondió mi mensaje.";
  emotionSelect.value = "ansiedad";
  supportModeSelect.value = "acción";
  responseToneSelect.value = "acompañamiento";
  intensityRange.value = "88";
  intensityValue.textContent = "88";
});

clearHistoryBtn.addEventListener("click", () => {
  const ok = confirm("¿Borrar el historial de este perfil?");
  if (!ok) return;
  localStorage.removeItem(historyKey());
  renderHistory();
  renderPatterns();
  renderSimpleSummary();
});

sendBtn.addEventListener("click", async () => {
  const payload = collectPayload();

  if (!payload.situation && !payload.thought) {
    alert("Escribí al menos qué sucedió y cuál fue el pensamiento.");
    return;
  }

  if (containsCrisis(`${payload.situation} ${payload.before} ${payload.thought} ${payload.evidence}`)) {
    showCrisisMessage();
    return;
  }

  const history = getHistory();
  const patterns = analyzePatterns([...history, buildPendingRecord(payload)]);

  payload.patterns = patterns;
  payload.recentHistory = history.slice(0, 5).map((item) => ({
    date: item.createdAt,
    situation: item.situation,
    thought: item.thought,
    emotion: item.emotion,
    supportMode: item.supportMode,
    responseTone: item.responseTone,
    dynamicTerms: item.localAnalysis?.topTerms || [],
    distortions: item.localAnalysis?.distortions?.map((d) => d.label) || []
  }));

  await streamAIResponse(payload);

  saveRecord({
    ...payload,
    localAnalysis: analyzeSingleRecord(payload),
    aiPreview: chatOutput.innerText.slice(0, 900),
    createdAt: new Date().toISOString()
  });

  renderHistory();
  renderPatterns();
  renderSimpleSummary();
});

function collectPayload() {
  return {
    profileName: profileName.value.trim() || "Usuario",
    situation: situationInput.value.trim(),
    before: beforeInput.value.trim(),
    thought: thoughtInput.value.trim(),
    evidence: evidenceInput.value.trim(),
    emotion: emotionSelect.value,
    supportMode: supportModeSelect.value,
    responseTone: responseToneSelect.value,
    intensity: Number(intensityRange.value)
  };
}

async function streamAIResponse(payload) {
  setStatus("Acompañando…", "loading");
  chatOutput.innerHTML = `<div class="chat-message" id="currentMessage"></div>`;
  const currentMessage = document.querySelector("#currentMessage");
  let fullText = "";

  try {
    const response = await fetch("/api/chat", {
      method: "POST",
      headers: {
        "Content-Type": "application/json"
      },
      body: JSON.stringify(payload)
    });

    if (!response.ok || !response.body) {
      throw new Error("No se pudo iniciar la respuesta.");
    }

    const reader = response.body.getReader();
    const decoder = new TextDecoder();
    let buffer = "";

    while (true) {
      const { value, done } = await reader.read();
      if (done) break;

      buffer += decoder.decode(value, { stream: true });
      const events = buffer.split("\n\n");
      buffer = events.pop() || "";

      for (const eventBlock of events) {
        const line = eventBlock.split("\n").find((item) => item.startsWith("data: "));
        if (!line) continue;

        const data = JSON.parse(line.replace("data: ", ""));

        if (data.type === "delta") {
          fullText += data.text;
          currentMessage.innerHTML = formatMarkdown(fullText);
          chatOutput.scrollTop = chatOutput.scrollHeight;
        }

        if (data.type === "error") {
          throw new Error(data.text);
        }
      }
    }

    setStatus("Respuesta lista", "");
  } catch (error) {
    console.error(error);
    const fallback = buildLocalFallback(payload);
    currentMessage.innerHTML = formatMarkdown(fallback);
    setStatus("Modo local", "error");
  }
}

function saveRecord(record) {
  const history = getHistory();
  history.unshift(record);
  localStorage.setItem(historyKey(), JSON.stringify(history.slice(0, 80)));
}

function getHistory() {
  try {
    return JSON.parse(localStorage.getItem(historyKey())) || [];
  } catch {
    return [];
  }
}

function historyKey() {
  const name = normalize(profileName.value.trim() || "default");
  return `pc_history_${name}`;
}

function buildPendingRecord(payload) {
  return {
    ...payload,
    localAnalysis: analyzeSingleRecord(payload),
    createdAt: new Date().toISOString()
  };
}

function analyzeSingleRecord(record) {
  const text = `${record.situation || ""} ${record.before || ""} ${record.thought || ""} ${record.evidence || ""}`;
  const tokens = tokenize(text);
  const phrases = extractPhrases(tokens);

  const distortions = DISTORTIONS.map((distortion) => {
    const normalized = normalize(text);
    const score = distortion.words.reduce((count, word) => (
      normalized.includes(normalize(word)) ? count + 1 : count
    ), 0);

    return { ...distortion, score };
  }).filter((distortion) => distortion.score > 0);

  const topTerms = rankTerms([...tokens, ...phrases]).slice(0, 8);

  return {
    tokens,
    phrases,
    topTerms,
    distortions
  };
}

function analyzePatterns(records) {
  const analyzed = records.map((record) => ({
    ...record,
    localAnalysis: record.localAnalysis || analyzeSingleRecord(record)
  }));

  const termMap = new Map();
  const phraseMap = new Map();
  const distortionMap = new Map();

  analyzed.forEach((record) => {
    const uniqueTerms = new Set((record.localAnalysis.tokens || []).filter(isMeaningfulAnchor));
    const uniquePhrases = new Set((record.localAnalysis.phrases || []).filter(isMeaningfulPhrase));

    uniqueTerms.forEach((term) => {
      const item = termMap.get(term) || {
        label: term,
        count: 0,
        examples: [],
        type: "tema recurrente"
      };
      item.count += 1;
      if (record.thought && item.examples.length < 3) item.examples.push(record.thought);
      termMap.set(term, item);
    });

    uniquePhrases.forEach((phrase) => {
      const item = phraseMap.get(phrase) || {
        label: phrase,
        count: 0,
        examples: [],
        type: "frase significativa"
      };
      item.count += 1;
      if (record.thought && item.examples.length < 3) item.examples.push(record.thought);
      phraseMap.set(phrase, item);
    });

    (record.localAnalysis.distortions || []).forEach((distortion) => {
      const item = distortionMap.get(distortion.id) || {
        label: distortion.label,
        count: 0,
        score: 0
      };
      item.count += 1;
      item.score += distortion.score;
      distortionMap.set(distortion.id, item);
    });
  });

  const repeatedPhrases = [...phraseMap.values()]
    .filter((item) => item.count >= 2)
    .sort((a, b) => b.count - a.count || b.label.length - a.label.length);

  const repeatedTerms = [...termMap.values()]
    .filter((item) => item.count >= 3)
    .sort((a, b) => b.count - a.count);

  const topDistortions = [...distortionMap.values()]
    .sort((a, b) => b.count - a.count || b.score - a.score)
    .slice(0, 5);

  const clusters = buildSimilarityClusters(analyzed);
  const cyclePatterns = buildCyclePatterns(analyzed, topDistortions);

  const dynamicPatterns = [
    ...cyclePatterns,
    ...topDistortions
      .filter((item) => item.count >= 2)
      .map((item) => ({
        label: item.label,
        count: item.count,
        type: "patrón de pensamiento",
        examples: []
      })),
    ...clusters.slice(0, 4),
    ...repeatedPhrases.slice(0, 3),
    ...repeatedTerms.slice(0, 2)
  ]
    .filter((item) => item.count >= 2)
    .filter(uniqueByLabel)
    .sort((a, b) => {
      const priority = {
        "ciclo recurrente": 4,
        "patrón de pensamiento": 3,
        "grupo similar": 2,
        "frase significativa": 1,
        "tema recurrente": 0
      };

      return (priority[b.type] || 0) - (priority[a.type] || 0) || b.count - a.count;
    })
    .slice(0, 8);

  return {
    totalRecords: records.length,
    dynamicPatterns,
    topDistortions,
    repeatedTerms: repeatedTerms.slice(0, 10),
    repeatedPhrases: repeatedPhrases.slice(0, 10),
    similarThoughts: findSimilarThoughts(analyzed),
    thoughtMap: buildThoughtMap(analyzed, dynamicPatterns, topDistortions)
  };
}

function buildCyclePatterns(records, topDistortions) {
  if (records.length < 3) return [];

  const emotionMap = new Map();
  records.forEach((record) => {
    const key = record.emotion || "sin emoción";
    const item = emotionMap.get(key) || { emotion: key, count: 0, records: [] };
    item.count += 1;
    item.records.push(record);
    emotionMap.set(key, item);
  });

  const topEmotion = [...emotionMap.values()].sort((a, b) => b.count - a.count)[0];
  const topDistortion = topDistortions.find((item) => item.count >= 2);

  if (!topEmotion || topEmotion.count < 2 || !topDistortion) return [];

  const relatedRecords = records.filter((record) =>
    record.emotion === topEmotion.emotion &&
    (record.localAnalysis?.distortions || []).some((distortion) => distortion.label === topDistortion.label)
  );

  if (relatedRecords.length < 2) return [];

  const anchors = rankTerms(
    relatedRecords.flatMap((record) => record.localAnalysis?.tokens || [])
      .filter(isMeaningfulAnchor)
  ).slice(0, 3);

  const anchorText = anchors.length ? ` alrededor de ${anchors.join(" / ")}` : "";
  return [{
    label: `${topEmotion.emotion} + ${topDistortion.label}${anchorText}`,
    count: relatedRecords.length,
    type: "ciclo recurrente",
    examples: relatedRecords.slice(0, 3).map((record) => record.thought || record.situation || "")
  }];
}

function isMeaningfulPhrase(phrase) {
  const parts = phrase.split(" ");
  if (parts.length < 2) return false;
  return parts.some(isMeaningfulAnchor) && !parts.every((part) => STOPWORDS.has(part));
}

function isMeaningfulAnchor(term) {
  if (!term || term.length < 5) return false;
  if (STOPWORDS.has(term)) return false;

  const genericWords = new Set([
    "venia", "venía", "estaba", "estaban", "aparece", "aparecio", "apareció",
    "siento", "sentia", "sentía", "pensaba", "pensar", "decir", "hacer",
    "pasado", "pasaba", "pasaron", "registro", "respuesta", "persona",
    "situacion", "situación", "evidencia", "emocion", "emoción"
  ]);

  if (genericWords.has(term)) return false;

  const genericEndings = [
    "ando", "iendo", "mente", "aban", "adas", "ados"
  ];

  if (genericEndings.some((ending) => term.endsWith(ending))) return false;

  return true;
}

function buildSimilarityClusters(records) {
  const clusters = [];

  records.forEach((record) => {
    const tokens = new Set(record.localAnalysis?.tokens || []);
    if (tokens.size < 2) return;

    let matchedCluster = null;

    for (const cluster of clusters) {
      const similarity = jaccard(tokens, cluster.tokenSet);
      if (similarity >= 0.22) {
        matchedCluster = cluster;
        break;
      }
    }

    if (matchedCluster) {
      matchedCluster.records.push(record);
      matchedCluster.tokenSet = new Set([...matchedCluster.tokenSet, ...tokens]);
    } else {
      clusters.push({
        records: [record],
        tokenSet: tokens
      });
    }
  });

  return clusters
    .filter((cluster) => cluster.records.length >= 2)
    .map((cluster) => {
      const allTokens = cluster.records
        .flatMap((record) => record.localAnalysis?.tokens || [])
        .filter(isMeaningfulAnchor);
      const label = buildClusterLabel(allTokens);
      return {
        label,
        count: cluster.records.length,
        type: "grupo similar",
        examples: cluster.records.slice(0, 3).map((record) => record.thought || record.situation || "")
      };
    })
    .filter((cluster) => cluster.label);
}

function buildClusterLabel(tokens) {
  const ranked = rankTerms(tokens).slice(0, 3);
  if (!ranked.length) return "";
  return ranked.join(" / ");
}

function findSimilarThoughts(records) {
  if (records.length < 2) return [];

  const latest = records[0];
  const latestTokens = new Set(tokenize(`${latest.situation || ""} ${latest.thought || ""}`));

  return records.slice(1).map((record) => {
    const tokens = new Set(tokenize(`${record.situation || ""} ${record.thought || ""}`));
    const similarity = jaccard(latestTokens, tokens);

    return {
      thought: record.thought,
      date: record.createdAt,
      similarity: Number(similarity.toFixed(2))
    };
  })
    .filter((item) => item.similarity >= 0.18)
    .slice(0, 4);
}


function buildThoughtMap(records, dynamicPatterns, topDistortions) {
  if (!records.length) {
    return {
      enoughData: false,
      message: "Todavía no hay registros suficientes para crear un mapa.",
      nodes: [],
      links: []
    };
  }

  const situationTerms = collectRankedTerms(records, ["situation", "before"]).slice(0, 4);
  const thoughtTerms = collectRankedTerms(records, ["thought"]).slice(0, 4);
  const emotionCounts = countBy(records.map((record) => record.emotion).filter(Boolean));
  const topEmotion = emotionCounts[0]?.label || "emoción no registrada";
  const topDistortion = topDistortions[0]?.label || "sin patrón de pensamiento repetido claro";
  const topPattern = dynamicPatterns[0]?.label || thoughtTerms.slice(0, 2).join(" / ") || "patrón todavía difuso";

  const triggerLabel = situationTerms.length
    ? situationTerms.join(" / ")
    : "situaciones todavía variadas";

  const thoughtLabel = thoughtTerms.length
    ? thoughtTerms.join(" / ")
    : topPattern;

  const alternative = buildMapAlternative(triggerLabel, thoughtLabel, topEmotion, topDistortion);

  const nodes = [
    {
      id: "trigger",
      title: "Situación que activa",
      value: triggerLabel,
      detail: records.length >= 2
        ? "Contextos significativos que aparecen en los registros."
        : "Con más registros, esta parte se vuelve más precisa."
    },
    {
      id: "thought",
      title: "Pensamiento automático",
      value: thoughtLabel,
      detail: "Lo que la mente suele interpretar o anticipar."
    },
    {
      id: "emotion",
      title: "Emoción dominante",
      value: topEmotion,
      detail: "La emoción que más aparece en el historial de este perfil."
    },
    {
      id: "distortion",
      title: "Patrón de pensamiento posible",
      value: topDistortion,
      detail: "No es diagnóstico: es una pista sobre la forma repetida de interpretar."
    },
    {
      id: "alternative",
      title: "Respuesta alternativa",
      value: alternative,
      detail: "Frase base para cortar el ciclo antes de creer el peor escenario."
    }
  ];

  return {
    enoughData: records.length >= 2,
    totalRecords: records.length,
    confidence: Math.min(100, Math.round((records.length / 6) * 100)),
    nodes,
    links: [
      "Situación → pensamiento",
      "Pensamiento → emoción",
      "Emoción → patrón de pensamiento",
      "Patrón de pensamiento → alternativa"
    ]
  };
}

function collectRankedTerms(records, fields) {
  const terms = [];

  records.forEach((record) => {
    const text = fields.map((field) => record[field] || "").join(" ");
    terms.push(...tokenize(text).filter(isMeaningfulAnchor));
  });

  return rankTerms(terms);
}

function countBy(values) {
  const map = new Map();

  values.forEach((value) => {
    const key = value || "sin dato";
    map.set(key, (map.get(key) || 0) + 1);
  });

  return [...map.entries()]
    .sort((a, b) => b[1] - a[1])
    .map(([label, count]) => ({ label, count }));
}

function buildMapAlternative(trigger, thought, emotion, distortion) {
  const cleanTrigger = trigger === "situaciones todavía variadas" ? "esta situación" : trigger;
  const cleanThought = thought === "patrón todavía difuso" ? "el peor escenario" : thought;

  return `Cuando aparezca ${cleanTrigger}, puedo notar que mi ${emotion} quizá está empujando el pensamiento hacia “${cleanThought}”. Antes de creerlo como hecho, puedo buscar evidencia y elegir una acción concreta.`;
}

function renderSimpleSummary() {
  const history = getHistory();
  const patterns = analyzePatterns(history);

  if (!history.length) {
    simpleSummaryPanel.innerHTML = `
      <div class="empty-state compact-empty">
        <span>🌿</span>
        <p>Cuando guardes algunos registros, acá va a aparecer un resumen simple.</p>
      </div>
    `;
    return;
  }

  if (history.length < 3) {
    simpleSummaryPanel.innerHTML = `
      <article class="simple-summary-card">
        <strong>Todavía es temprano para sacar conclusiones.</strong>
        <p>Tenés ${history.length} registro${history.length === 1 ? "" : "s"}. La app no va a forzar un patrón con tan poca información.</p>
      </article>
    `;
    return;
  }

  const emotionCounts = countBy(history.map((record) => record.emotion).filter(Boolean));
  const topEmotion = emotionCounts[0]?.label || "una emoción todavía variada";
  const topPattern = patterns.dynamicPatterns[0]?.label || patterns.topDistortions[0]?.label || "";
  const latest = history[0];

  if (!topPattern) {
    simpleSummaryPanel.innerHTML = `
      <article class="simple-summary-card">
        <strong>No aparece un patrón claro todavía.</strong>
        <p>Eso también es información: tus registros por ahora son variados. La app va a esperar más datos antes de señalar algo.</p>
      </article>
    `;
    return;
  }

  simpleSummaryPanel.innerHTML = `
    <article class="simple-summary-card">
      <span class="summary-pill">${history.length} registros</span>
      <h3>Algo que se repite</h3>
      <p>Cuando aparece <strong>${escapeHtml(topEmotion)}</strong>, suele aparecer algo relacionado con <strong>${escapeHtml(topPattern)}</strong>.</p>
    </article>

    <article class="simple-summary-card">
      <h3>Último pensamiento</h3>
      <p>${escapeHtml(latest.thought || latest.situation || "Registro sin pensamiento escrito.")}</p>
    </article>

    <article class="simple-summary-card calming">
      <h3>Idea amable</h3>
      <p>No hace falta convertir esto en una conclusión. Podés tomarlo como una pista para observarte con más calma.</p>
    </article>
  `;
}

function renderPatterns() {
  const patterns = analyzePatterns(getHistory());

  if (patterns.totalRecords === 0) {
    patternsPanel.innerHTML = `<p class="empty-small">Todavía no hay registros para detectar patrones.</p>`;
    return;
  }

  if (patterns.totalRecords < 3) {
    patternsPanel.innerHTML = `<p class="empty-small">Necesitás al menos 3 registros para detectar patrones útiles. Con 1 o 2 registros solo hay señales sueltas.</p>`;
    return;
  }

  const blocks = [];

  if (patterns.dynamicPatterns.length) {
    blocks.push(`<p class="patterns-note">Se muestran solo repeticiones con sentido: ciclos, patrones de pensamiento o pensamientos realmente parecidos. Las palabras comunes se ignoran.</p>`);
    blocks.push(...patterns.dynamicPatterns.map((pattern) => patternBlock(
      pattern.label,
      `${pattern.type || "patrón"} · aparece en ${pattern.count} registro${pattern.count === 1 ? "" : "s"}.`,
      Math.min(100, pattern.count * 28)
    )));
  }

  if (!blocks.length) {
    blocks.push(`<p class="empty-small">Hay registros, pero todavía no aparece un patrón útil. La app ya no muestra palabras sueltas como “venía” porque eso puede ser solo coincidencia.</p>`);
  }

  patternsPanel.innerHTML = blocks.join("");
}

function patternBlock(title, description, width) {
  return `
    <article class="pattern-item">
      <strong>${escapeHtml(title)}</strong>
      <p>${escapeHtml(description)}</p>
      <div class="pattern-meter"><span style="width:${width}%"></span></div>
    </article>
  `;
}

function renderHistory() {
  const history = getHistory();
  historyList.innerHTML = "";

  if (!history.length) {
    historyList.innerHTML = `<p class="empty-small">Todavía no hay pensamientos registrados.</p>`;
    return;
  }

  history.slice(0, 15).forEach((item) => {
    const node = historyTemplate.content.cloneNode(true);
    const date = new Date(item.createdAt);
    const dateText = Number.isNaN(date.getTime())
      ? "Sin fecha"
      : date.toLocaleString("es-UY", { dateStyle: "short", timeStyle: "short" });

    node.querySelector(".history-thought").textContent = item.thought || item.situation || "Registro sin título";
    node.querySelector(".history-meta").textContent = `${dateText} · ${item.emotion} · ${item.intensity}/100`;

    node.querySelector(".load-history").addEventListener("click", () => {
      loadHistoryItem(item);
    });

    historyList.appendChild(node);
  });
}

function loadHistoryItem(item) {
  situationInput.value = item.situation || "";
  beforeInput.value = item.before || "";
  thoughtInput.value = item.thought || "";
  evidenceInput.value = item.evidence || "";
  emotionSelect.value = item.emotion || "ansiedad";
  supportModeSelect.value = item.supportMode || "automático";
  responseToneSelect.value = item.responseTone || "acompañamiento";
  intensityRange.value = item.intensity || 80;
  intensityValue.textContent = intensityRange.value;

  chatOutput.innerHTML = `
    <div class="chat-message">
      <h3>Registro anterior</h3>
      <p><strong>Situación:</strong> ${escapeHtml(item.situation || "")}</p>
      <p><strong>Pensamiento:</strong> ${escapeHtml(item.thought || "")}</p>
      <p><strong>Respuesta guardada:</strong></p>
      <p>${escapeHtml(item.aiPreview || "No hay vista previa guardada.")}</p>
    </div>
  `;

  document.querySelector(".main-panel").scrollIntoView({ behavior: "smooth" });
}

function containsCrisis(text) {
  const lower = normalize(text);

  // No activar crisis cuando la persona niega explícitamente el riesgo.
  // Ej: "no quiero hacerme daño" no es lo mismo que "quiero hacerme daño".
  if (CRISIS_NEGATION_PATTERNS.some((pattern) => lower.includes(normalize(pattern)))) {
    const positiveWithoutNegation = CRISIS_PATTERNS.some((pattern) => {
      const normalizedPattern = normalize(pattern);
      const index = lower.indexOf(normalizedPattern);
      if (index === -1) return false;
      const contextBefore = lower.slice(Math.max(0, index - 28), index);
      return !/\b(no|nunca|jamas|jamás|sin)\b/.test(contextBefore);
    });

    return positiveWithoutNegation && !lower.includes("no ");
  }

  return CRISIS_PATTERNS.some((pattern) => {
    const normalizedPattern = normalize(pattern);
    const index = lower.indexOf(normalizedPattern);
    if (index === -1) return false;

    const contextBefore = lower.slice(Math.max(0, index - 32), index);
    const isNegated = /\b(no|nunca|jamas|jamás|sin)\b/.test(contextBefore);

    return !isNegated;
  });
}

function showCrisisMessage() {
  setStatus("Priorizar seguridad", "error");
  chatOutput.innerHTML = formatMarkdown(`### Esto parece más urgente que un ejercicio de pensamiento

Esto se activa solo cuando la app interpreta una señal afirmativa de riesgo. Si estabas diciendo que NO querés hacerte daño, podés seguir conversando normalmente.

Si hay riesgo de que te hagas daño o de que dañes a otra persona, buscá ayuda inmediata: llamá a emergencias locales, contactá a alguien de confianza o acercate a un servicio de salud.

No tenés que resolver esto desde una app.`);
}

async function sendFeelingsMessage() {
  const message = feelingsInput.value.trim();
  if (!message) return;

  const userMessage = {
    role: "user",
    text: message,
    createdAt: new Date().toISOString()
  };

  const conversation = getFeelingsConversation();
  conversation.push(userMessage);
  saveFeelingsConversation(conversation);
  feelingsInput.value = "";
  renderFeelingsConversation(true);

  const assistantMessage = {
    role: "assistant",
    text: "",
    createdAt: new Date().toISOString()
  };
  conversation.push(assistantMessage);
  saveFeelingsConversation(conversation);
  renderFeelingsConversation(true);

  try {
    const payload = {
      profileName: profileName.value.trim() || "Usuario",
      message,
      emotion: emotionSelect.value,
      responseTone: responseToneSelect.value,
      conversation: conversation.slice(0, -1),
      recentHistory: getHistory().slice(0, 5)
    };

    const response = await fetch("/api/feelings-chat", {
      method: "POST",
      headers: {
        "Content-Type": "application/json"
      },
      body: JSON.stringify(payload)
    });

    if (!response.ok || !response.body) {
      throw new Error("No se pudo iniciar la conversación.");
    }

    const reader = response.body.getReader();
    const decoder = new TextDecoder();
    let buffer = "";
    let fullText = "";

    while (true) {
      const { value, done } = await reader.read();
      if (done) break;

      buffer += decoder.decode(value, { stream: true });
      const events = buffer.split("\n\n");
      buffer = events.pop() || "";

      for (const eventBlock of events) {
        const line = eventBlock.split("\n").find((item) => item.startsWith("data: "));
        if (!line) continue;

        const data = JSON.parse(line.replace("data: ", ""));

        if (data.type === "delta") {
          fullText += data.text;
          assistantMessage.text = fullText;
          saveFeelingsConversation(conversation);
          renderFeelingsConversation(true);
        }

        if (data.type === "error") {
          throw new Error(data.text);
        }
      }
    }
  } catch (error) {
    console.error(error);
    assistantMessage.text = buildFeelingsFallback(message);
    saveFeelingsConversation(conversation);
    renderFeelingsConversation(true);
  }
}

function getFeelingsConversation() {
  try {
    return JSON.parse(localStorage.getItem(feelingsKey())) || [];
  } catch {
    return [];
  }
}

function saveFeelingsConversation(conversation) {
  localStorage.setItem(feelingsKey(), JSON.stringify(conversation.slice(-40)));
}

function feelingsKey() {
  const name = normalize(profileName.value.trim() || "default");
  return `pc_feelings_${name}`;
}

function renderFeelingsConversation(scrollToEnd = false) {
  const conversation = getFeelingsConversation();

  if (!conversation.length) {
    feelingsMessages.innerHTML = `
      <div class="feelings-empty">
        <span>🫶</span>
        <p>Podés escribir algo como: “hoy me siento feliz pero acelerada” o “no sé por qué estoy sensible”.</p>
      </div>
    `;
    return;
  }

  feelingsMessages.innerHTML = conversation.map((message) => `
    <article class="feelings-bubble ${message.role === "user" ? "user-bubble" : "assistant-bubble"}">
      <p>${formatMarkdown(message.text || "Pensando…")}</p>
    </article>
  `).join("");

  if (scrollToEnd) {
    feelingsMessages.scrollTop = feelingsMessages.scrollHeight;
  }
}

function buildFeelingsFallback(message) {
  const lower = normalize(message);

  if (lower.includes("feliz") || lower.includes("content") || lower.includes("entusiasm")) {
    return "Qué bueno que aparezca algo positivo. También está bien mirar esa emoción con calma: disfrutarla no significa tomar decisiones impulsivas. ¿Querés celebrarlo, ordenarlo o pensar qué hacer con esa energía?";
  }

  if (lower.includes("enojo") || lower.includes("bronca") || lower.includes("frustr")) {
    return "Tiene sentido darle lugar a ese enojo. A veces el enojo señala un límite o una necesidad. Antes de actuar, capaz podemos preguntarnos: ¿qué está intentando defender esta emoción?";
  }

  if (lower.includes("triste") || lower.includes("bajon") || lower.includes("desanim")) {
    return "Te leo. No voy a apurarte a estar bien. Capaz ahora alcanza con ponerle nombre a lo que duele. ¿Querés contar qué parte de esto te pesa más?";
  }

  return "Te leo. Podemos ir de a poco: ¿querés que te ayude a ordenar lo que sentís, entender qué pensamiento aparece detrás o pensar una acción pequeña?";
}

function buildLocalFallback(payload) {
  const analysis = analyzeSingleRecord(payload);
  const patterns = analyzePatterns([...getHistory(), buildPendingRecord(payload)]);
  const topPattern = patterns.dynamicPatterns[0]?.label || "todavía no hay un patrón claro";
  const topDistortion = analysis.distortions[0]?.label || "un salto a una conclusión dolorosa";
  const fear = inferLocalFear(`${payload.situation || ""} ${payload.before || ""} ${payload.thought || ""}`);
  const action = suggestLocalAction(`${payload.situation || ""} ${payload.thought || ""}`, payload.supportMode);
  const opener = payload.responseTone === "directo"
    ? "Vamos a ir a lo concreto."
    : payload.responseTone === "suave"
      ? "Tiene sentido que esto te haya dejado con ansiedad. Vamos despacio."
      : "Ok, paremos un segundo: tu mente está intentando resolver rápido algo que todavía tiene huecos.";

  return `### Vamos despacio

${opener}

Lo que pasó fue: **${payload.situation || "no se completó la situación"}**.  
El pensamiento que apareció fue: **“${payload.thought || "no se completó el pensamiento"}”**.

### Lo que parece estar doliendo

Más abajo del pensamiento puede haber este miedo: **${fear}**.

### Dato vs película mental

**Dato:** ${payload.situation || "falta escribir el hecho observable"}.  
**Contexto:** ${payload.before || "no agregaste contexto previo"}.  
**Evidencia:** ${payload.evidence || "no escribiste evidencia directa"}.  
**Película mental:** que “${payload.thought || "el peor escenario"}” ya está confirmado.

Con lo que escribiste, todavía no se puede confirmar esa conclusión.

### Patrón de pensamiento posible

Este registro se parece a: **${topDistortion}**.  
Patrón útil detectado en historial: **${topPattern}**.

### Una frase más creíble

“No tengo que creerle al peor escenario solo porque se siente fuerte. Puedo volver al dato y decidir el próximo paso.”

### Qué podés hacer ahora

${action}`;
}

function inferLocalFear(text) {
  const lower = normalize(text);

  if (lower.includes("jefe") || lower.includes("desped") || lower.includes("trabajo")) {
    return "que un error te quite seguridad, valor o confianza en el trabajo";
  }

  if (lower.includes("visto") || lower.includes("mensaje") || lower.includes("responde")) {
    return "que el silencio de otra persona signifique rechazo";
  }

  if (lower.includes("cliente") || lower.includes("precio") || lower.includes("comprar")) {
    return "que la falta de respuesta signifique que tu trabajo no vale";
  }

  if (lower.includes("examen") || lower.includes("prueba") || lower.includes("materia")) {
    return "que un resultado puntual confirme que no vas a poder";
  }

  return "que esta situación confirme algo negativo sobre vos o sobre lo que puede pasar";
}

function suggestLocalAction(text, mode) {
  const lower = normalize(text);

  if (mode === "contención") {
    return "Antes de resolver, bajá un poco la intensidad: escribí tres datos reales y una cosa que todavía no sabés. No decidas desde el pico de ansiedad.";
  }

  if (lower.includes("jefe") || lower.includes("trabajo") || lower.includes("desped")) {
    return `Si necesitás actuar, podés escribir algo simple: “Quería aclarar lo que pasó y saber si necesitás que haga algo más para resolverlo.”`;
  }

  if (lower.includes("visto") || lower.includes("mensaje") || lower.includes("responde")) {
    return "Poné un plazo concreto para esperar antes de volver a escribir. Mientras tanto, separá dato de interpretación.";
  }

  return "Elegí una acción de menos de cinco minutos: pedir un dato, escribir qué falta saber o hacer una corrección concreta.";
}

function formatMarkdown(markdown) {
  let html = escapeHtml(markdown);

  html = html
    .replace(/^### (.*)$/gm, "<h3>$1</h3>")
    .replace(/\*\*(.*?)\*\*/g, "<strong>$1</strong>")
    .replace(/^- (.*)$/gm, "<li>$1</li>")
    .replace(/^\d+\. (.*)$/gm, "<li>$1</li>")
    .replace(/\n\n/g, "</p><p>")
    .replace(/\n/g, "<br>");

  html = `<p>${html}</p>`;
  html = html.replace(/<p><h3>/g, "<h3>").replace(/<\/h3><\/p>/g, "</h3>");
  html = html.replace(/<p><li>/g, "<ul><li>").replace(/<\/li><\/p>/g, "</li></ul>");
  html = html.replace(/<\/li><br><li>/g, "</li><li>");
  return html;
}

function tokenize(text) {
  return normalize(text)
    .replace(/[^\w\sñ]/gi, " ")
    .split(/\s+/)
    .map((token) => token.trim())
    .filter((token) => token.length > 3 && !STOPWORDS.has(token))
    .slice(0, 120);
}

function extractPhrases(tokens) {
  const phrases = [];

  for (let size = 2; size <= 3; size += 1) {
    for (let index = 0; index <= tokens.length - size; index += 1) {
      const slice = tokens.slice(index, index + size);
      if (slice.every((token) => token.length > 3 && !STOPWORDS.has(token))) {
        phrases.push(slice.join(" "));
      }
    }
  }

  return phrases;
}

function rankTerms(terms) {
  const map = new Map();

  terms.forEach((term) => {
    if (!term || term.length < 4) return;
    map.set(term, (map.get(term) || 0) + 1);
  });

  return [...map.entries()]
    .sort((a, b) => b[1] - a[1] || b[0].length - a[0].length)
    .map(([term]) => term);
}

function jaccard(setA, setB) {
  if (!setA.size && !setB.size) return 0;
  const intersection = [...setA].filter((token) => setB.has(token)).length;
  const union = new Set([...setA, ...setB]).size || 1;
  return intersection / union;
}

function uniqueByLabel(item, index, array) {
  return array.findIndex((other) => other.label === item.label) === index;
}

function normalize(text) {
  return String(text)
    .toLowerCase()
    .normalize("NFD")
    .replace(/[\u0300-\u036f]/g, "");
}

function escapeHtml(text) {
  return String(text)
    .replaceAll("&", "&amp;")
    .replaceAll("<", "&lt;")
    .replaceAll(">", "&gt;")
    .replaceAll('"', "&quot;")
    .replaceAll("'", "&#039;");
}

function setStatus(text, className) {
  aiStatus.textContent = text;
  aiStatus.className = `status-pill ${className || ""}`;
}

renderHistory();
renderPatterns();
renderSimpleSummary();
renderFeelingsConversation();
