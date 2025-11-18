FROM node:20

WORKDIR /app

# Copia package.json e package-lock
COPY package*.json ./

# Instala dependências
RUN npm install --production

# Copia o restante do código (src, prisma, etc)
COPY . .

# Gera o Prisma Client
RUN npx prisma generate

# Porta que o serviço irá escutar
EXPOSE 3007

# Comando padrão (o docker-compose pode sobrescrever se necessário)
CMD ["node", "src/index.js"]
