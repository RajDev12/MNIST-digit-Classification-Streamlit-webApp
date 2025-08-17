├── IBM_Internship_–_Sentiment_Analysis_using_Naive_Bayes.ipynb
├── IMDB_sample.csv
├── README.md
├── Sentiment-Analysis-of-Product-Reviews-using-Naive-Bayes.pdf (2).pdf
└── requirements.txt


/IBM_Internship_–_Sentiment_Analysis_using_Naive_Bayes.ipynb:
--------------------------------------------------------------------------------
  1 | {
  2 |   "nbformat": 4,
  3 |   "nbformat_minor": 0,
  4 |   "metadata": {
  5 |     "colab": {
  6 |       "provenance": []
  7 |     },
  8 |     "kernelspec": {
  9 |       "name": "python3",
 10 |       "display_name": "Python 3"
 11 |     },
 12 |     "language_info": {
 13 |       "name": "python"
 14 |     }
 15 |   },
 16 |   "cells": [
 17 |     {
 18 |       "cell_type": "code",
 19 |       "execution_count": 4,
 20 |       "metadata": {
 21 |         "colab": {
 22 |           "base_uri": "https://localhost:8080/",
 23 |           "height": 206
 24 |         },
 25 |         "id": "E8m1wDVaENUv",
 26 |         "outputId": "08853b0d-e64c-478c-d3ab-0ab3b8a9f829"
 27 |       },
 28 |       "outputs": [
 29 |         {
 30 |           "output_type": "execute_result",
 31 |           "data": {
 32 |             "text/plain": [
 33 |               "                                              review sentiment\n",
 34 |               "0  One of the other reviewers has mentioned that ...  positive\n",
 35 |               "1  A wonderful little production. <br /><br />The...  positive\n",
 36 |               "2  I thought this was a wonderful way to spend ti...  positive\n",
 37 |               "3  Basically there's a family where a little boy ...  negative\n",
 38 |               "4  Petter Mattei's \"Love in the Time of Money\" is...  positive"
 39 |             ],
 40 |             "text/html": [
 41 |               "\n",
 42 |               "  <div id=\"df-ba22d161-98f7-49c7-ac25-191b3aa4bacf\" class=\"colab-df-container\">\n",
 43 |               "    <div>\n",
 44 |               "<style scoped>\n",
 45 |               "    .dataframe tbody tr th:only-of-type {\n",
 46 |               "        vertical-align: middle;\n",
 47 |               "    }\n",
 48 |               "\n",
 49 |               "    .dataframe tbody tr th {\n",
 50 |               "        vertical-align: top;\n",
 51 |               "    }\n",
 52 |               "\n",
 53 |               "    .dataframe thead th {\n",
 54 |               "        text-align: right;\n",
 55 |               "    }\n",
 56 |               "</style>\n",
 57 |               "<table border=\"1\" class=\"dataframe\">\n",
 58 |               "  <thead>\n",
 59 |               "    <tr style=\"text-align: right;\">\n",
 60 |               "      <th></th>\n",
 61 |               "      <th>review</th>\n",
 62 |               "      <th>sentiment</th>\n",
 63 |               "    </tr>\n",
 64 |               "  </thead>\n",
 65 |               "  <tbody>\n",
 66 |               "    <tr>\n",
 67 |               "      <th>0</th>\n",
 68 |               "      <td>One of the other reviewers has mentioned that ...</td>\n",
 69 |               "      <td>positive</td>\n",
 70 |               "    </tr>\n",
 71 |               "    <tr>\n",
 72 |               "      <th>1</th>\n",
 73 |               "      <td>A wonderful little production. &lt;br /&gt;&lt;br /&gt;The...</td>\n",
 74 |               "      <td>positive</td>\n",
 75 |               "    </tr>\n",
 76 |               "    <tr>\n",
 77 |               "      <th>2</th>\n",
 78 |               "      <td>I thought this was a wonderful way to spend ti...</td>\n",
 79 |               "      <td>positive</td>\n",
 80 |               "    </tr>\n",
 81 |               "    <tr>\n",
 82 |               "      <th>3</th>\n",
 83 |               "      <td>Basically there's a family where a little boy ...</td>\n",
 84 |               "      <td>negative</td>\n",
 85 |               "    </tr>\n",
 86 |               "    <tr>\n",
 87 |               "      <th>4</th>\n",
 88 |               "      <td>Petter Mattei's \"Love in the Time of Money\" is...</td>\n",
 89 |               "      <td>positive</td>\n",
 90 |               "    </tr>\n",
 91 |               "  </tbody>\n",
 92 |               "</table>\n",
 93 |               "</div>\n",
 94 |               "    <div class=\"colab-df-buttons\">\n",
 95 |               "      \n",
 96 |               "  <div class=\"colab-df-container\">\n",
 97 |               "    <button class=\"colab-df-convert\" onclick=\"convertToInteractive('df-ba22d161-98f7-49c7-ac25-191b3aa4bacf')\"\n",
 98 |               "            title=\"Convert this dataframe to an interactive table.\"\n",
 99 |               "            style=\"display:none;\">\n",
100 |               "      \n",
101 |               "  <svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\" viewBox=\"0 -960 960 960\">\n",
102 |               "    <path d=\"M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z\"/>\n",
103 |               "  </svg>\n",
104 |               "    </button>\n",
105 |               "    \n",
106 |               "  <style>\n",
107 |               "    .colab-df-container {\n",
108 |               "      display:flex;\n",
109 |               "      gap: 12px;\n",
110 |               "    }\n",
111 |               "\n",
112 |               "    .colab-df-convert {\n",
113 |               "      background-color: #E8F0FE;\n",
114 |               "      border: none;\n",
115 |               "      border-radius: 50%;\n",
116 |               "      cursor: pointer;\n",
117 |               "      display: none;\n",
118 |               "      fill: #1967D2;\n",
119 |               "      height: 32px;\n",
120 |               "      padding: 0 0 0 0;\n",
121 |               "      width: 32px;\n",
122 |               "    }\n",
123 |               "\n",
124 |               "    .colab-df-convert:hover {\n",
125 |               "      background-color: #E2EBFA;\n",
126 |               "      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
127 |               "      fill: #174EA6;\n",
128 |               "    }\n",
129 |               "\n",
130 |               "    .colab-df-buttons div {\n",
131 |               "      margin-bottom: 4px;\n",
132 |               "    }\n",
133 |               "\n",
134 |               "    [theme=dark] .colab-df-convert {\n",
135 |               "      background-color: #3B4455;\n",
136 |               "      fill: #D2E3FC;\n",
137 |               "    }\n",
138 |               "\n",
139 |               "    [theme=dark] .colab-df-convert:hover {\n",
140 |               "      background-color: #434B5C;\n",
141 |               "      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);\n",
142 |               "      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));\n",
143 |               "      fill: #FFFFFF;\n",
144 |               "    }\n",
145 |               "  </style>\n",
146 |               "\n",
147 |               "    <script>\n",
148 |               "      const buttonEl =\n",
149 |               "        document.querySelector('#df-ba22d161-98f7-49c7-ac25-191b3aa4bacf button.colab-df-convert');\n",
150 |               "      buttonEl.style.display =\n",
151 |               "        google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
152 |               "\n",
153 |               "      async function convertToInteractive(key) {\n",
154 |               "        const element = document.querySelector('#df-ba22d161-98f7-49c7-ac25-191b3aa4bacf');\n",
155 |               "        const dataTable =\n",
156 |               "          await google.colab.kernel.invokeFunction('convertToInteractive',\n",
157 |               "                                                    [key], {});\n",
158 |               "        if (!dataTable) return;\n",
159 |               "\n",
160 |               "        const docLinkHtml = 'Like what you see? Visit the ' +\n",
161 |               "          '<a target=\"_blank\" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'\n",
162 |               "          + ' to learn more about interactive tables.';\n",
163 |               "        element.innerHTML = '';\n",
164 |               "        dataTable['output_type'] = 'display_data';\n",
165 |               "        await google.colab.output.renderOutput(dataTable, element);\n",
166 |               "        const docLink = document.createElement('div');\n",
167 |               "        docLink.innerHTML = docLinkHtml;\n",
168 |               "        element.appendChild(docLink);\n",
169 |               "      }\n",
170 |               "    </script>\n",
171 |               "  </div>\n",
172 |               "  \n",
173 |               "    </div>\n",
174 |               "  </div>\n",
175 |               "  "
176 |             ]
177 |           },
178 |           "metadata": {},
179 |           "execution_count": 4
180 |         }
181 |       ],
182 |       "source": [
183 |         "import pandas as pd\n",
184 |         "\n",
185 |         "df = pd.read_csv('/content/IMDB_Dataset[1].csv')\n",
186 |         "df.head()\n",
187 |         "\n",
188 |         "\n",
189 |         "\n"
190 |       ]
191 |     },
192 |     {
193 |       "cell_type": "code",
194 |       "source": [
195 |         "import nltk\n",
196 |         "import nltk\n",
197 |         "nltk.download('punkt')\n",
198 |         "nltk.download('stopwords')\n",
199 |         "\n"
200 |       ],
201 |       "metadata": {
202 |         "colab": {
203 |           "base_uri": "https://localhost:8080/"
204 |         },
205 |         "id": "q-SKaTY8kk5f",
206 |         "outputId": "f7f7d0ff-ce69-440f-8b1d-57194c574a9c"
207 |       },
208 |       "execution_count": 6,
209 |       "outputs": [
210 |         {
211 |           "output_type": "stream",
212 |           "name": "stderr",
213 |           "text": [
214 |             "[nltk_data] Downloading package punkt to /root/nltk_data...\n",
215 |             "[nltk_data]   Package punkt is already up-to-date!\n",
216 |             "[nltk_data] Downloading package stopwords to /root/nltk_data...\n",
217 |             "[nltk_data]   Package stopwords is already up-to-date!\n"
218 |           ]
219 |         },
220 |         {
221 |           "output_type": "execute_result",
222 |           "data": {
223 |             "text/plain": [
224 |               "True"
225 |             ]
226 |           },
227 |           "metadata": {},
228 |           "execution_count": 6
229 |         }
230 |       ]
231 |     },
232 |     {
233 |       "cell_type": "code",
234 |       "source": [
235 |         "from nltk.corpus import stopwords\n",
236 |         "from nltk.stem.porter import PorterStemmer\n",
237 |         "\n",
238 |         "stop_words = set(stopwords.words('english'))\n",
239 |         "stemmer = PorterStemmer()\n",
240 |         "\n",
241 |         "def preprocess_text(text):\n",
242 |         "    tokens = text.lower().split()  # replaced word_tokenize to avoid punkt_tab error\n",
243 |         "    words = [stemmer.stem(w) for w in tokens if w.isalpha() and w not in stop_words]\n",
244 |         "    return ' '.join(words)\n",
245 |         "\n",
246 |         "df['cleaned_review'] = df['review'].apply(preprocess_text)\n",
247 |         "df[['review', 'cleaned_review']].head()\n",
248 |         "\n",
249 |         "\n",
250 |         "\n"
251 |       ],
252 |       "metadata": {
253 |         "colab": {
254 |           "base_uri": "https://localhost:8080/",
255 |           "height": 206
256 |         },
257 |         "id": "nTiL2RhzkrhJ",
258 |         "outputId": "4ba94069-86f0-4aa2-ffe0-b3fecd860c17"
259 |       },
260 |       "execution_count": 8,
261 |       "outputs": [
262 |         {
263 |           "output_type": "execute_result",
264 |           "data": {
265 |             "text/plain": [
266 |               "                                              review  \\\n",
267 |               "0  One of the other reviewers has mentioned that ...   \n",
268 |               "1  A wonderful little production. <br /><br />The...   \n",
269 |               "2  I thought this was a wonderful way to spend ti...   \n",
270 |               "3  Basically there's a family where a little boy ...   \n",
271 |               "4  Petter Mattei's \"Love in the Time of Money\" is...   \n",
272 |               "\n",
273 |               "                                      cleaned_review  \n",
274 |               "0  one review mention watch oz episod exactli hap...  \n",
275 |               "1  wonder littl film techniqu fashion give someti...  \n",
276 |               "2  thought wonder way spend time hot summer sit a...  \n",
277 |               "3  basic famili littl boy think zombi closet pare...  \n",
278 |               "4  petter time visual stun film mattei offer us v...  "
279 |             ],
280 |             "text/html": [
281 |               "\n",
282 |               "  <div id=\"df-b212de54-2858-4679-b905-c13cb3b752b7\" class=\"colab-df-container\">\n",
283 |               "    <div>\n",
284 |               "<style scoped>\n",
285 |               "    .dataframe tbody tr th:only-of-type {\n",
286 |               "        vertical-align: middle;\n",
287 |               "    }\n",
288 |               "\n",
289 |               "    .dataframe tbody tr th {\n",
290 |               "        vertical-align: top;\n",
291 |               "    }\n",
292 |               "\n",
293 |               "    .dataframe thead th {\n",
294 |               "        text-align: right;\n",
295 |               "    }\n",
296 |               "</style>\n",
297 |               "<table border=\"1\" class=\"dataframe\">\n",
298 |               "  <thead>\n",
299 |               "    <tr style=\"text-align: right;\">\n",
300 |               "      <th></th>\n",
301 |               "      <th>review</th>\n",
302 |               "      <th>cleaned_review</th>\n",
303 |               "    </tr>\n",
304 |               "  </thead>\n",
305 |               "  <tbody>\n",
306 |               "    <tr>\n",
307 |               "      <th>0</th>\n",
308 |               "      <td>One of the other reviewers has mentioned that ...</td>\n",
309 |               "      <td>one review mention watch oz episod exactli hap...</td>\n",
310 |               "    </tr>\n",
311 |               "    <tr>\n",
312 |               "      <th>1</th>\n",
313 |               "      <td>A wonderful little production. &lt;br /&gt;&lt;br /&gt;The...</td>\n",
314 |               "      <td>wonder littl film techniqu fashion give someti...</td>\n",
315 |               "    </tr>\n",
316 |               "    <tr>\n",
317 |               "      <th>2</th>\n",
318 |               "      <td>I thought this was a wonderful way to spend ti...</td>\n",
319 |               "      <td>thought wonder way spend time hot summer sit a...</td>\n",
320 |               "    </tr>\n",
321 |               "    <tr>\n",
322 |               "      <th>3</th>\n",
323 |               "      <td>Basically there's a family where a little boy ...</td>\n",
324 |               "      <td>basic famili littl boy think zombi closet pare...</td>\n",
325 |               "    </tr>\n",
326 |               "    <tr>\n",
327 |               "      <th>4</th>\n",
328 |               "      <td>Petter Mattei's \"Love in the Time of Money\" is...</td>\n",
329 |               "      <td>petter time visual stun film mattei offer us v...</td>\n",
330 |               "    </tr>\n",
331 |               "  </tbody>\n",
332 |               "</table>\n",
333 |               "</div>\n",
334 |               "    <div class=\"colab-df-buttons\">\n",
335 |               "      \n",
336 |               "  <div class=\"colab-df-container\">\n",
337 |               "    <button class=\"colab-df-convert\" onclick=\"convertToInteractive('df-b212de54-2858-4679-b905-c13cb3b752b7')\"\n",
338 |               "            title=\"Convert this dataframe to an interactive table.\"\n",
339 |               "            style=\"display:none;\">\n",
340 |               "      \n",
341 |               "  <svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\" viewBox=\"0 -960 960 960\">\n",
342 |               "    <path d=\"M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z\"/>\n",
343 |               "  </svg>\n",
344 |               "    </button>\n",
345 |               "    \n",
346 |               "  <style>\n",
347 |               "    .colab-df-container {\n",
348 |               "      display:flex;\n",
349 |               "      gap: 12px;\n",
350 |               "    }\n",
351 |               "\n",
352 |               "    .colab-df-convert {\n",
353 |               "      background-color: #E8F0FE;\n",
354 |               "      border: none;\n",
355 |               "      border-radius: 50%;\n",
356 |               "      cursor: pointer;\n",
357 |               "      display: none;\n",
358 |               "      fill: #1967D2;\n",
359 |               "      height: 32px;\n",
360 |               "      padding: 0 0 0 0;\n",
361 |               "      width: 32px;\n",
362 |               "    }\n",
363 |               "\n",
364 |               "    .colab-df-convert:hover {\n",
365 |               "      background-color: #E2EBFA;\n",
366 |               "      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
367 |               "      fill: #174EA6;\n",
368 |               "    }\n",
369 |               "\n",
370 |               "    .colab-df-buttons div {\n",
371 |               "      margin-bottom: 4px;\n",
372 |               "    }\n",
373 |               "\n",
374 |               "    [theme=dark] .colab-df-convert {\n",
375 |               "      background-color: #3B4455;\n",
376 |               "      fill: #D2E3FC;\n",
377 |               "    }\n",
378 |               "\n",
379 |               "    [theme=dark] .colab-df-convert:hover {\n",
380 |               "      background-color: #434B5C;\n",
381 |               "      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);\n",
382 |               "      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));\n",
383 |               "      fill: #FFFFFF;\n",
384 |               "    }\n",
385 |               "  </style>\n",
386 |               "\n",
387 |               "    <script>\n",
388 |               "      const buttonEl =\n",
389 |               "        document.querySelector('#df-b212de54-2858-4679-b905-c13cb3b752b7 button.colab-df-convert');\n",
390 |               "      buttonEl.style.display =\n",
391 |               "        google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
392 |               "\n",
393 |               "      async function convertToInteractive(key) {\n",
394 |               "        const element = document.querySelector('#df-b212de54-2858-4679-b905-c13cb3b752b7');\n",
395 |               "        const dataTable =\n",
396 |               "          await google.colab.kernel.invokeFunction('convertToInteractive',\n",
397 |               "                                                    [key], {});\n",
398 |               "        if (!dataTable) return;\n",
399 |               "\n",
400 |               "        const docLinkHtml = 'Like what you see? Visit the ' +\n",
401 |               "          '<a target=\"_blank\" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'\n",
402 |               "          + ' to learn more about interactive tables.';\n",
403 |               "        element.innerHTML = '';\n",
404 |               "        dataTable['output_type'] = 'display_data';\n",
405 |               "        await google.colab.output.renderOutput(dataTable, element);\n",
406 |               "        const docLink = document.createElement('div');\n",
407 |               "        docLink.innerHTML = docLinkHtml;\n",
408 |               "        element.appendChild(docLink);\n",
409 |               "      }\n",
410 |               "    </script>\n",
411 |               "  </div>\n",
412 |               "  \n",
413 |               "    </div>\n",
414 |               "  </div>\n",
415 |               "  "
416 |             ]
417 |           },
418 |           "metadata": {},
419 |           "execution_count": 8
420 |         }
421 |       ]
422 |     },
423 |     {
424 |       "cell_type": "code",
425 |       "source": [
426 |         "from sklearn.feature_extraction.text import TfidfVectorizer\n",
427 |         "\n",
428 |         "# Initialize TF-IDF Vectorizer\n",
429 |         "vectorizer = TfidfVectorizer(max_features=5000)\n",
430 |         "\n",
431 |         "# Fit and transform the cleaned reviews\n",
432 |         "X = vectorizer.fit_transform(df['cleaned_review']).toarray()\n",
433 |         "\n",
434 |         "# Target labels: convert 'positive' → 1, 'negative' → 0\n",
435 |         "y = df['sentiment'].map({'positive': 1, 'negative': 0})\n"
436 |       ],
437 |       "metadata": {
438 |         "id": "8P6Rr3MIrt4R"
439 |       },
440 |       "execution_count": 9,
441 |       "outputs": []
442 |     },
443 |     {
444 |       "cell_type": "code",
445 |       "source": [
446 |         "from sklearn.model_selection import train_test_split\n",
447 |         "from sklearn.naive_bayes import MultinomialNB\n",
448 |         "\n",
449 |         "# Split data: 80% training, 20% testing\n",
450 |         "X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)\n",
451 |         "\n",
452 |         "# Initialize and train the Naive Bayes model\n",
453 |         "model = MultinomialNB()\n",
454 |         "model.fit(X_train, y_train)\n"
455 |       ],
456 |       "metadata": {
457 |         "colab": {
458 |           "base_uri": "https://localhost:8080/",
459 |           "height": 80
460 |         },
461 |         "id": "PKXjWzTsr_F7",
462 |         "outputId": "f33f1713-1115-4141-8fb2-d27bb8cf1d4b"
463 |       },
464 |       "execution_count": 10,
465 |       "outputs": [
466 |         {
467 |           "output_type": "execute_result",
468 |           "data": {
469 |             "text/plain": [
470 |               "MultinomialNB()"
471 |             ],
472 |             "text/html": [
473 |               "<style>#sk-container-id-1 {\n",
474 |               "  /* Definition of color scheme common for light and dark mode */\n",
475 |               "  --sklearn-color-text: #000;\n",
476 |               "  --sklearn-color-text-muted: #666;\n",
477 |               "  --sklearn-color-line: gray;\n",
478 |               "  /* Definition of color scheme for unfitted estimators */\n",
479 |               "  --sklearn-color-unfitted-level-0: #fff5e6;\n",
480 |               "  --sklearn-color-unfitted-level-1: #f6e4d2;\n",
481 |               "  --sklearn-color-unfitted-level-2: #ffe0b3;\n",
482 |               "  --sklearn-color-unfitted-level-3: chocolate;\n",
483 |               "  /* Definition of color scheme for fitted estimators */\n",
484 |               "  --sklearn-color-fitted-level-0: #f0f8ff;\n",
485 |               "  --sklearn-color-fitted-level-1: #d4ebff;\n",
486 |               "  --sklearn-color-fitted-level-2: #b3dbfd;\n",
487 |               "  --sklearn-color-fitted-level-3: cornflowerblue;\n",
488 |               "\n",
489 |               "  /* Specific color for light theme */\n",
490 |               "  --sklearn-color-text-on-default-background: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, black)));\n",
491 |               "  --sklearn-color-background: var(--sg-background-color, var(--theme-background, var(--jp-layout-color0, white)));\n",
492 |               "  --sklearn-color-border-box: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, black)));\n",
493 |               "  --sklearn-color-icon: #696969;\n",
494 |               "\n",
495 |               "  @media (prefers-color-scheme: dark) {\n",
496 |               "    /* Redefinition of color scheme for dark theme */\n",
497 |               "    --sklearn-color-text-on-default-background: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, white)));\n",
498 |               "    --sklearn-color-background: var(--sg-background-color, var(--theme-background, var(--jp-layout-color0, #111)));\n",
499 |               "    --sklearn-color-border-box: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, white)));\n",
500 |               "    --sklearn-color-icon: #878787;\n",
501 |               "  }\n",
502 |               "}\n",
503 |               "\n",
504 |               "#sk-container-id-1 {\n",
505 |               "  color: var(--sklearn-color-text);\n",
506 |               "}\n",
507 |               "\n",
508 |               "#sk-container-id-1 pre {\n",
509 |               "  padding: 0;\n",
510 |               "}\n",
511 |               "\n",
512 |               "#sk-container-id-1 input.sk-hidden--visually {\n",
513 |               "  border: 0;\n",
514 |               "  clip: rect(1px 1px 1px 1px);\n",
515 |               "  clip: rect(1px, 1px, 1px, 1px);\n",
516 |               "  height: 1px;\n",
517 |               "  margin: -1px;\n",
518 |               "  overflow: hidden;\n",
519 |               "  padding: 0;\n",
520 |               "  position: absolute;\n",
521 |               "  width: 1px;\n",
522 |               "}\n",
523 |               "\n",
524 |               "#sk-container-id-1 div.sk-dashed-wrapped {\n",
525 |               "  border: 1px dashed var(--sklearn-color-line);\n",
526 |               "  margin: 0 0.4em 0.5em 0.4em;\n",
527 |               "  box-sizing: border-box;\n",
528 |               "  padding-bottom: 0.4em;\n",
529 |               "  background-color: var(--sklearn-color-background);\n",
530 |               "}\n",
531 |               "\n",
532 |               "#sk-container-id-1 div.sk-container {\n",
533 |               "  /* jupyter's `normalize.less` sets `[hidden] { display: none; }`\n",
534 |               "     but bootstrap.min.css set `[hidden] { display: none !important; }`\n",
535 |               "     so we also need the `!important` here to be able to override the\n",
536 |               "     default hidden behavior on the sphinx rendered scikit-learn.org.\n",
537 |               "     See: https://github.com/scikit-learn/scikit-learn/issues/21755 */\n",
538 |               "  display: inline-block !important;\n",
539 |               "  position: relative;\n",
540 |               "}\n",
541 |               "\n",
542 |               "#sk-container-id-1 div.sk-text-repr-fallback {\n",
543 |               "  display: none;\n",
544 |               "}\n",
545 |               "\n",
546 |               "div.sk-parallel-item,\n",
547 |               "div.sk-serial,\n",
548 |               "div.sk-item {\n",
549 |               "  /* draw centered vertical line to link estimators */\n",
550 |               "  background-image: linear-gradient(var(--sklearn-color-text-on-default-background), var(--sklearn-color-text-on-default-background));\n",
551 |               "  background-size: 2px 100%;\n",
552 |               "  background-repeat: no-repeat;\n",
553 |               "  background-position: center center;\n",
554 |               "}\n",
555 |               "\n",
556 |               "/* Parallel-specific style estimator block */\n",
557 |               "\n",
558 |               "#sk-container-id-1 div.sk-parallel-item::after {\n",
559 |               "  content: \"\";\n",
560 |               "  width: 100%;\n",
561 |               "  border-bottom: 2px solid var(--sklearn-color-text-on-default-background);\n",
562 |               "  flex-grow: 1;\n",
563 |               "}\n",
564 |               "\n",
565 |               "#sk-container-id-1 div.sk-parallel {\n",
566 |               "  display: flex;\n",
567 |               "  align-items: stretch;\n",
568 |               "  justify-content: center;\n",
569 |               "  background-color: var(--sklearn-color-background);\n",
570 |               "  position: relative;\n",
571 |               "}\n",
572 |               "\n",
573 |               "#sk-container-id-1 div.sk-parallel-item {\n",
574 |               "  display: flex;\n",
575 |               "  flex-direction: column;\n",
576 |               "}\n",
577 |               "\n",
578 |               "#sk-container-id-1 div.sk-parallel-item:first-child::after {\n",
579 |               "  align-self: flex-end;\n",
580 |               "  width: 50%;\n",
581 |               "}\n",
582 |               "\n",
583 |               "#sk-container-id-1 div.sk-parallel-item:last-child::after {\n",
584 |               "  align-self: flex-start;\n",
585 |               "  width: 50%;\n",
586 |               "}\n",
587 |               "\n",
588 |               "#sk-container-id-1 div.sk-parallel-item:only-child::after {\n",
589 |               "  width: 0;\n",
590 |               "}\n",
591 |               "\n",
592 |               "/* Serial-specific style estimator block */\n",
593 |               "\n",
594 |               "#sk-container-id-1 div.sk-serial {\n",
595 |               "  display: flex;\n",
596 |               "  flex-direction: column;\n",
597 |               "  align-items: center;\n",
598 |               "  background-color: var(--sklearn-color-background);\n",
599 |               "  padding-right: 1em;\n",
600 |               "  padding-left: 1em;\n",
601 |               "}\n",
602 |               "\n",
603 |               "\n",
604 |               "/* Toggleable style: style used for estimator/Pipeline/ColumnTransformer box that is\n",
605 |               "clickable and can be expanded/collapsed.\n",
606 |               "- Pipeline and ColumnTransformer use this feature and define the default style\n",
607 |               "- Estimators will overwrite some part of the style using the `sk-estimator` class\n",
608 |               "*/\n",
609 |               "\n",
610 |               "/* Pipeline and ColumnTransformer style (default) */\n",
611 |               "\n",
612 |               "#sk-container-id-1 div.sk-toggleable {\n",
613 |               "  /* Default theme specific background. It is overwritten whether we have a\n",
614 |               "  specific estimator or a Pipeline/ColumnTransformer */\n",
615 |               "  background-color: var(--sklearn-color-background);\n",
616 |               "}\n",
617 |               "\n",
618 |               "/* Toggleable label */\n",
619 |               "#sk-container-id-1 label.sk-toggleable__label {\n",
620 |               "  cursor: pointer;\n",
621 |               "  display: flex;\n",
622 |               "  width: 100%;\n",
623 |               "  margin-bottom: 0;\n",
624 |               "  padding: 0.5em;\n",
625 |               "  box-sizing: border-box;\n",
626 |               "  text-align: center;\n",
627 |               "  align-items: start;\n",
628 |               "  justify-content: space-between;\n",
629 |               "  gap: 0.5em;\n",
630 |               "}\n",
631 |               "\n",
632 |               "#sk-container-id-1 label.sk-toggleable__label .caption {\n",
633 |               "  font-size: 0.6rem;\n",
634 |               "  font-weight: lighter;\n",
635 |               "  color: var(--sklearn-color-text-muted);\n",
636 |               "}\n",
637 |               "\n",
638 |               "#sk-container-id-1 label.sk-toggleable__label-arrow:before {\n",
639 |               "  /* Arrow on the left of the label */\n",
640 |               "  content: \"▸\";\n",
641 |               "  float: left;\n",
642 |               "  margin-right: 0.25em;\n",
643 |               "  color: var(--sklearn-color-icon);\n",
644 |               "}\n",
645 |               "\n",
646 |               "#sk-container-id-1 label.sk-toggleable__label-arrow:hover:before {\n",
647 |               "  color: var(--sklearn-color-text);\n",
648 |               "}\n",
649 |               "\n",
650 |               "/* Toggleable content - dropdown */\n",
651 |               "\n",
652 |               "#sk-container-id-1 div.sk-toggleable__content {\n",
653 |               "  max-height: 0;\n",
654 |               "  max-width: 0;\n",
655 |               "  overflow: hidden;\n",
656 |               "  text-align: left;\n",
657 |               "  /* unfitted */\n",
658 |               "  background-color: var(--sklearn-color-unfitted-level-0);\n",
659 |               "}\n",
660 |               "\n",
661 |               "#sk-container-id-1 div.sk-toggleable__content.fitted {\n",
662 |               "  /* fitted */\n",
663 |               "  background-color: var(--sklearn-color-fitted-level-0);\n",
664 |               "}\n",
665 |               "\n",
666 |               "#sk-container-id-1 div.sk-toggleable__content pre {\n",
667 |               "  margin: 0.2em;\n",
668 |               "  border-radius: 0.25em;\n",
669 |               "  color: var(--sklearn-color-text);\n",
670 |               "  /* unfitted */\n",
671 |               "  background-color: var(--sklearn-color-unfitted-level-0);\n",
672 |               "}\n",
673 |               "\n",
674 |               "#sk-container-id-1 div.sk-toggleable__content.fitted pre {\n",
675 |               "  /* unfitted */\n",
676 |               "  background-color: var(--sklearn-color-fitted-level-0);\n",
677 |               "}\n",
678 |               "\n",
679 |               "#sk-container-id-1 input.sk-toggleable__control:checked~div.sk-toggleable__content {\n",
680 |               "  /* Expand drop-down */\n",
681 |               "  max-height: 200px;\n",
682 |               "  max-width: 100%;\n",
683 |               "  overflow: auto;\n",
684 |               "}\n",
685 |               "\n",
686 |               "#sk-container-id-1 input.sk-toggleable__control:checked~label.sk-toggleable__label-arrow:before {\n",
687 |               "  content: \"▾\";\n",
688 |               "}\n",
689 |               "\n",
690 |               "/* Pipeline/ColumnTransformer-specific style */\n",
691 |               "\n",
692 |               "#sk-container-id-1 div.sk-label input.sk-toggleable__control:checked~label.sk-toggleable__label {\n",
693 |               "  color: var(--sklearn-color-text);\n",
694 |               "  background-color: var(--sklearn-color-unfitted-level-2);\n",
695 |               "}\n",
696 |               "\n",
697 |               "#sk-container-id-1 div.sk-label.fitted input.sk-toggleable__control:checked~label.sk-toggleable__label {\n",
698 |               "  background-color: var(--sklearn-color-fitted-level-2);\n",
699 |               "}\n",
700 |               "\n",
701 |               "/* Estimator-specific style */\n",
702 |               "\n",
703 |               "/* Colorize estimator box */\n",
704 |               "#sk-container-id-1 div.sk-estimator input.sk-toggleable__control:checked~label.sk-toggleable__label {\n",
705 |               "  /* unfitted */\n",
706 |               "  background-color: var(--sklearn-color-unfitted-level-2);\n",
707 |               "}\n",
708 |               "\n",
709 |               "#sk-container-id-1 div.sk-estimator.fitted input.sk-toggleable__control:checked~label.sk-toggleable__label {\n",
710 |               "  /* fitted */\n",
711 |               "  background-color: var(--sklearn-color-fitted-level-2);\n",
712 |               "}\n",
713 |               "\n",
714 |               "#sk-container-id-1 div.sk-label label.sk-toggleable__label,\n",
715 |               "#sk-container-id-1 div.sk-label label {\n",
716 |               "  /* The background is the default theme color */\n",
717 |               "  color: var(--sklearn-color-text-on-default-background);\n",
718 |               "}\n",
719 |               "\n",
720 |               "/* On hover, darken the color of the background */\n",
721 |               "#sk-container-id-1 div.sk-label:hover label.sk-toggleable__label {\n",
722 |               "  color: var(--sklearn-color-text);\n",
723 |               "  background-color: var(--sklearn-color-unfitted-level-2);\n",
724 |               "}\n",
725 |               "\n",
726 |               "/* Label box, darken color on hover, fitted */\n",
727 |               "#sk-container-id-1 div.sk-label.fitted:hover label.sk-toggleable__label.fitted {\n",
728 |               "  color: var(--sklearn-color-text);\n",
729 |               "  background-color: var(--sklearn-color-fitted-level-2);\n",
730 |               "}\n",
731 |               "\n",
732 |               "/* Estimator label */\n",
733 |               "\n",
734 |               "#sk-container-id-1 div.sk-label label {\n",
735 |               "  font-family: monospace;\n",
736 |               "  font-weight: bold;\n",
737 |               "  display: inline-block;\n",
738 |               "  line-height: 1.2em;\n",
739 |               "}\n",
740 |               "\n",
741 |               "#sk-container-id-1 div.sk-label-container {\n",
742 |               "  text-align: center;\n",
743 |               "}\n",
744 |               "\n",
745 |               "/* Estimator-specific */\n",
746 |               "#sk-container-id-1 div.sk-estimator {\n",
747 |               "  font-family: monospace;\n",
748 |               "  border: 1px dotted var(--sklearn-color-border-box);\n",
749 |               "  border-radius: 0.25em;\n",
750 |               "  box-sizing: border-box;\n",
751 |               "  margin-bottom: 0.5em;\n",
752 |               "  /* unfitted */\n",
753 |               "  background-color: var(--sklearn-color-unfitted-level-0);\n",
754 |               "}\n",
755 |               "\n",
756 |               "#sk-container-id-1 div.sk-estimator.fitted {\n",
757 |               "  /* fitted */\n",
758 |               "  background-color: var(--sklearn-color-fitted-level-0);\n",
759 |               "}\n",
760 |               "\n",
761 |               "/* on hover */\n",
762 |               "#sk-container-id-1 div.sk-estimator:hover {\n",
763 |               "  /* unfitted */\n",
764 |               "  background-color: var(--sklearn-color-unfitted-level-2);\n",
765 |               "}\n",
766 |               "\n",
767 |               "#sk-container-id-1 div.sk-estimator.fitted:hover {\n",
768 |               "  /* fitted */\n",
769 |               "  background-color: var(--sklearn-color-fitted-level-2);\n",
770 |               "}\n",
771 |               "\n",
772 |               "/* Specification for estimator info (e.g. \"i\" and \"?\") */\n",
773 |               "\n",
774 |               "/* Common style for \"i\" and \"?\" */\n",
775 |               "\n",
776 |               ".sk-estimator-doc-link,\n",
777 |               "a:link.sk-estimator-doc-link,\n",
778 |               "a:visited.sk-estimator-doc-link {\n",
779 |               "  float: right;\n",
780 |               "  font-size: smaller;\n",
781 |               "  line-height: 1em;\n",
782 |               "  font-family: monospace;\n",
783 |               "  background-color: var(--sklearn-color-background);\n",
784 |               "  border-radius: 1em;\n",
785 |               "  height: 1em;\n",
786 |               "  width: 1em;\n",
787 |               "  text-decoration: none !important;\n",
788 |               "  margin-left: 0.5em;\n",
789 |               "  text-align: center;\n",
790 |               "  /* unfitted */\n",
791 |               "  border: var(--sklearn-color-unfitted-level-1) 1pt solid;\n",
792 |               "  color: var(--sklearn-color-unfitted-level-1);\n",
793 |               "}\n",
794 |               "\n",
795 |               ".sk-estimator-doc-link.fitted,\n",
796 |               "a:link.sk-estimator-doc-link.fitted,\n",
797 |               "a:visited.sk-estimator-doc-link.fitted {\n",
798 |               "  /* fitted */\n",
799 |               "  border: var(--sklearn-color-fitted-level-1) 1pt solid;\n",
800 |               "  color: var(--sklearn-color-fitted-level-1);\n",
801 |               "}\n",
802 |               "\n",
803 |               "/* On hover */\n",
804 |               "div.sk-estimator:hover .sk-estimator-doc-link:hover,\n",
805 |               ".sk-estimator-doc-link:hover,\n",
806 |               "div.sk-label-container:hover .sk-estimator-doc-link:hover,\n",
807 |               ".sk-estimator-doc-link:hover {\n",
808 |               "  /* unfitted */\n",
809 |               "  background-color: var(--sklearn-color-unfitted-level-3);\n",
810 |               "  color: var(--sklearn-color-background);\n",
811 |               "  text-decoration: none;\n",
812 |               "}\n",
813 |               "\n",
814 |               "div.sk-estimator.fitted:hover .sk-estimator-doc-link.fitted:hover,\n",
815 |               ".sk-estimator-doc-link.fitted:hover,\n",
816 |               "div.sk-label-container:hover .sk-estimator-doc-link.fitted:hover,\n",
817 |               ".sk-estimator-doc-link.fitted:hover {\n",
818 |               "  /* fitted */\n",
819 |               "  background-color: var(--sklearn-color-fitted-level-3);\n",
820 |               "  color: var(--sklearn-color-background);\n",
821 |               "  text-decoration: none;\n",
822 |               "}\n",
823 |               "\n",
824 |               "/* Span, style for the box shown on hovering the info icon */\n",
825 |               ".sk-estimator-doc-link span {\n",
826 |               "  display: none;\n",
827 |               "  z-index: 9999;\n",
828 |               "  position: relative;\n",
829 |               "  font-weight: normal;\n",
830 |               "  right: .2ex;\n",
831 |               "  padding: .5ex;\n",
832 |               "  margin: .5ex;\n",
833 |               "  width: min-content;\n",
834 |               "  min-width: 20ex;\n",
835 |               "  max-width: 50ex;\n",
836 |               "  color: var(--sklearn-color-text);\n",
837 |               "  box-shadow: 2pt 2pt 4pt #999;\n",
838 |               "  /* unfitted */\n",
839 |               "  background: var(--sklearn-color-unfitted-level-0);\n",
840 |               "  border: .5pt solid var(--sklearn-color-unfitted-level-3);\n",
841 |               "}\n",
842 |               "\n",
843 |               ".sk-estimator-doc-link.fitted span {\n",
844 |               "  /* fitted */\n",
845 |               "  background: var(--sklearn-color-fitted-level-0);\n",
846 |               "  border: var(--sklearn-color-fitted-level-3);\n",
847 |               "}\n",
848 |               "\n",
849 |               ".sk-estimator-doc-link:hover span {\n",
850 |               "  display: block;\n",
851 |               "}\n",
852 |               "\n",
853 |               "/* \"?\"-specific style due to the `<a>` HTML tag */\n",
854 |               "\n",
855 |               "#sk-container-id-1 a.estimator_doc_link {\n",
856 |               "  float: right;\n",
857 |               "  font-size: 1rem;\n",
858 |               "  line-height: 1em;\n",
859 |               "  font-family: monospace;\n",
860 |               "  background-color: var(--sklearn-color-background);\n",
861 |               "  border-radius: 1rem;\n",
862 |               "  height: 1rem;\n",
863 |               "  width: 1rem;\n",
864 |               "  text-decoration: none;\n",
865 |               "  /* unfitted */\n",
866 |               "  color: var(--sklearn-color-unfitted-level-1);\n",
867 |               "  border: var(--sklearn-color-unfitted-level-1) 1pt solid;\n",
868 |               "}\n",
869 |               "\n",
870 |               "#sk-container-id-1 a.estimator_doc_link.fitted {\n",
871 |               "  /* fitted */\n",
872 |               "  border: var(--sklearn-color-fitted-level-1) 1pt solid;\n",
873 |               "  color: var(--sklearn-color-fitted-level-1);\n",
874 |               "}\n",
875 |               "\n",
876 |               "/* On hover */\n",
877 |               "#sk-container-id-1 a.estimator_doc_link:hover {\n",
878 |               "  /* unfitted */\n",
879 |               "  background-color: var(--sklearn-color-unfitted-level-3);\n",
880 |               "  color: var(--sklearn-color-background);\n",
881 |               "  text-decoration: none;\n",
882 |               "}\n",
883 |               "\n",
884 |               "#sk-container-id-1 a.estimator_doc_link.fitted:hover {\n",
885 |               "  /* fitted */\n",
886 |               "  background-color: var(--sklearn-color-fitted-level-3);\n",
887 |               "}\n",
888 |               "</style><div id=\"sk-container-id-1\" class=\"sk-top-container\"><div class=\"sk-text-repr-fallback\"><pre>MultinomialNB()</pre><b>In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook. <br />On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.</b></div><div class=\"sk-container\" hidden><div class=\"sk-item\"><div class=\"sk-estimator fitted sk-toggleable\"><input class=\"sk-toggleable__control sk-hidden--visually\" id=\"sk-estimator-id-1\" type=\"checkbox\" checked><label for=\"sk-estimator-id-1\" class=\"sk-toggleable__label fitted sk-toggleable__label-arrow\"><div><div>MultinomialNB</div></div><div><a class=\"sk-estimator-doc-link fitted\" rel=\"noreferrer\" target=\"_blank\" href=\"https://scikit-learn.org/1.6/modules/generated/sklearn.naive_bayes.MultinomialNB.html\">?<span>Documentation for MultinomialNB</span></a><span class=\"sk-estimator-doc-link fitted\">i<span>Fitted</span></span></div></label><div class=\"sk-toggleable__content fitted\"><pre>MultinomialNB()</pre></div> </div></div></div></div>"
889 |             ]
890 |           },
891 |           "metadata": {},
892 |           "execution_count": 10
893 |         }
894 |       ]
895 |     },
896 |     {
897 |       "cell_type": "code",
898 |       "source": [
899 |         "from sklearn.metrics import accuracy_score, precision_score, recall_score, confusion_matrix\n",
900 |         "\n",
901 |         "# Predict sentiments for the test set\n",
902 |         "y_pred = model.predict(X_test)\n",
903 |         "\n",
904 |         "# Evaluate the model\n",
905 |         "accuracy = accuracy_score(y_test, y_pred)\n",
906 |         "precision = precision_score(y_test, y_pred, pos_label=1)\n",
907 |         "recall = recall_score(y_test, y_pred, pos_label=1)\n",
908 |         "conf_matrix = confusion_matrix(y_test, y_pred)\n",
909 |         "\n",
910 |         "print(f\"Accuracy: {accuracy:.4f}\")\n",
911 |         "print(f\"Precision: {precision:.4f}\")\n",
912 |         "print(f\"Recall: {recall:.4f}\")\n",
913 |         "print(\"Confusion Matrix:\")\n",
914 |         "print(conf_matrix)\n"
915 |       ],
916 |       "metadata": {
917 |         "colab": {
918 |           "base_uri": "https://localhost:8080/"
919 |         },
920 |         "id": "mhm92QyNsdn2",
921 |         "outputId": "a13f705e-a25a-4481-802f-2028122ac1e7"
922 |       },
923 |       "execution_count": 12,
924 |       "outputs": [
925 |         {
926 |           "output_type": "stream",
927 |           "name": "stdout",
928 |           "text": [
929 |             "Accuracy: 0.8345\n",
930 |             "Precision: 0.8324\n",
931 |             "Recall: 0.8408\n",
932 |             "Confusion Matrix:\n",
933 |             "[[4108  853]\n",
934 |             " [ 802 4237]]\n"
935 |           ]
936 |         }
937 |       ]
938 |     }
939 |   ]
940 | }


--------------------------------------------------------------------------------
/README.md:
--------------------------------------------------------------------------------
 1 | # Sentiment Analysis of Product Reviews using Naive Bayes
 2 | 
 3 | This project performs **sentiment analysis** on product reviews to determine whether a review is **positive or negative**. It uses **Natural Language Processing (NLP)** techniques and the **Naive Bayes** classification algorithm.
 4 | 
 5 | ---
 6 | 
 7 | ## Project Description
 8 | 
 9 | The main goal of this project is to analyze product reviews from a dataset and classify them based on sentiment. The classifier is trained to understand the difference between positive and negative reviews using real-world review data.
10 | 
11 | ---
12 | 
13 | ## 🛠️ Implementation Details
14 | 
15 | - **Programming Language**: Python
16 | - **Libraries Used**:
17 |   - `pandas` for data manipulation
18 |   - `nltk` for text preprocessing (tokenization, stopword removal, stemming)
19 |   - `scikit-learn` for model training and evaluation
20 | 
21 | - **Steps Followed**:
22 |   1. **Loading the dataset** of product reviews.
23 |   2. **Preprocessing the text**: removing stopwords, stemming, tokenizing.
24 |   3. **Feature Extraction** using TF-IDF (Term Frequency-Inverse Document Frequency).
25 |   4. **Model Training** using the Naive Bayes algorithm.
26 |   5. **Evaluation**: Using accuracy, precision, recall, and a confusion matrix.
27 | 
28 | ---
29 | 
30 | ## ⚙️ How to Run
31 | 
32 | 1. Clone the repo or open the [Colab Notebook](https://colab.research.google.com/drive/1Xe0fKV0T9ECjFuMOmNPP5qMj9y5EG7fw?usp=sharing)
33 | 2. Install the requirements:
34 | 
35 |    ```bash
36 |    pip install -r requirements.txt
37 | 3.Run the notebook or script.
38 | 
39 | 
40 | ## 💡 Challenges & Solutions
41 | 
42 | |   **Challenge**                    |   **Solution**                                                                 |
43 | |------------------------------------|--------------------------------------------------------------------------------|
44 | | **Handling large datasets**        | Filtered to a smaller subset for faster testing and reduced memory usage       |
45 | | **Noisy, unstructured review text**| Applied NLTK preprocessing: tokenization, stopword removal, and stemming       |
46 | | **Model overfitting on training set** | Tuned TF-IDF parameters and used Naive Bayes for simplicity and generalization |
47 | 
48 | 
49 | 
50 | 📁 **Files**
51 | **sentiment_analysis.ipynb** – Main notebook containing the implementation
52 | 
53 | **IMDB Dataset.csv** – Review dataset (trimmed for GitHub)
54 | 
55 | **requirements.txt** – List of required libraries
56 | 
57 | 📎 **Live Demo**
58 | Access the Colab version: [Click Here](https://colab.research.google.com/drive/1Xe0fKV0T9ECjFuMOmNPP5qMj9y5EG7fw?usp=sharing)
59 | 
60 | 
61 |  **Author**
62 | Reeti Singh
63 | BTech CSE | United Institute of Technology
64 | IBM Summer Internship Project – 2025
65 | 
66 | 
67 | 
68 | 


--------------------------------------------------------------------------------
/Sentiment-Analysis-of-Product-Reviews-using-Naive-Bayes.pdf (2).pdf:
--------------------------------------------------------------------------------
https://raw.githubusercontent.com/Reeti14/Sentiment-Analysis-NaiveBayes/935a8b8d3e9f0b5201b5c9029ed6a00b5ebcb7d2/Sentiment-Analysis-of-Product-Reviews-using-Naive-Bayes.pdf (2).pdf


--------------------------------------------------------------------------------
/requirements.txt:
--------------------------------------------------------------------------------
1 | nltk==3.8.1
2 | scikit-learn==1.4.1
3 | pandas==2.2.1
4 | numpy==1.26.4
5 | 
6 | 


--------------------------------------------------------------------------------
